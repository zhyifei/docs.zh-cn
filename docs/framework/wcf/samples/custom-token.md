---
title: 自定义令牌
ms.date: 03/30/2017
ms.assetid: e7fd8b38-c370-454f-ba3e-19759019f03d
ms.openlocfilehash: 8aa41a1f9651d0a385836178bc791c14706c17e4
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2018
ms.locfileid: "53243044"
---
# <a name="custom-token"></a><span data-ttu-id="4d5ee-102">自定义令牌</span><span class="sxs-lookup"><span data-stu-id="4d5ee-102">Custom Token</span></span>
<span data-ttu-id="4d5ee-103">此示例演示如何将添加到 Windows Communication Foundation (WCF) 应用程序自定义令牌的实现。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-103">This sample demonstrates how to add a custom token implementation into a Windows Communication Foundation (WCF) application.</span></span> <span data-ttu-id="4d5ee-104">示例使用 `CreditCardToken` 将客户端的信用卡相关信息安全地传递到服务。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-104">The example uses a `CreditCardToken` to securely pass information about client credit cards to the service.</span></span> <span data-ttu-id="4d5ee-105">令牌在 WS-Security 消息头中传递，并连同消息正文和其他消息头一起使用对称安全绑定元素进行签名和加密。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-105">The token is passed in the WS-Security message header and is signed and encrypted using the symmetric security binding element along with message body and other message headers.</span></span> <span data-ttu-id="4d5ee-106">当内置令牌不足时可以进行这样的操作。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-106">This is useful in cases where the built-in tokens are not sufficient.</span></span> <span data-ttu-id="4d5ee-107">本示例演示如何向服务提供自定义安全令牌而不必使用某个内置令牌。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-107">This sample demonstrates how to provide a custom security token to a service instead of using one of the built-in tokens.</span></span> <span data-ttu-id="4d5ee-108">该服务实现定义“请求-答复”通信模式的协定。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-108">The service implements a contract that defines a request-reply communication pattern.</span></span>

> [!NOTE]
>  <span data-ttu-id="4d5ee-109">本主题的最后介绍了此示例的设置过程和生成说明。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

 <span data-ttu-id="4d5ee-110">总之，此示例将演示如下内容：</span><span class="sxs-lookup"><span data-stu-id="4d5ee-110">To summarize, this sample demonstrates the following:</span></span>

-   <span data-ttu-id="4d5ee-111">客户端如何向服务传递自定义安全令牌。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-111">How a client can pass a custom security token to a service.</span></span>

-   <span data-ttu-id="4d5ee-112">服务如何使用和验证自定义安全令牌。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-112">How the service can consume and validate a custom security token.</span></span>

-   <span data-ttu-id="4d5ee-113">如何 WCF 服务代码可以获取有关接收到的安全令牌包括自定义安全令牌的信息。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-113">How the WCF service code can obtain the information about received security tokens including the custom security token.</span></span>

-   <span data-ttu-id="4d5ee-114">如何使用服务器的 X.509 证书保护用于消息加密和签名的对称密钥。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-114">How the server's X.509 certificate is used to protect the symmetric key used for message encryption and signature.</span></span>

## <a name="client-authentication-using-a-custom-security-token"></a><span data-ttu-id="4d5ee-115">使用自定义安全令牌的客户端身份验证</span><span class="sxs-lookup"><span data-stu-id="4d5ee-115">Client Authentication Using a Custom Security Token</span></span>
 <span data-ttu-id="4d5ee-116">服务公开单个终结点，此终结点是使用 `BindingHelper` 和 `EchoServiceHost` 类以编程方式创建的。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-116">The service exposes a single endpoint that is programmatically created using `BindingHelper` and `EchoServiceHost` classes.</span></span> <span data-ttu-id="4d5ee-117">终结点由地址、绑定和协定组成。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-117">The endpoint consists of an address, a binding, and a contract.</span></span> <span data-ttu-id="4d5ee-118">此绑定使用 `SymmetricSecurityBindingElement` 和 `HttpTransportBindingElement` 按照自定义绑定进行配置。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-118">The binding is configured with a custom binding using `SymmetricSecurityBindingElement` and `HttpTransportBindingElement`.</span></span> <span data-ttu-id="4d5ee-119">本示例将 `SymmetricSecurityBindingElement` 设置为使用服务的 X.509 证书在传输过程中保护对称密钥和在 WS-Security 消息头中传递自定义 `CreditCardToken` 作为签名和加密的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-119">This sample sets the `SymmetricSecurityBindingElement` to use a service's X.509 certificate to protect the symmetric key during transmission and to pass a custom `CreditCardToken` in a WS-Security message header as a signed and encrypted security token.</span></span> <span data-ttu-id="4d5ee-120">此行为指定用于客户端身份验证的服务凭据和有关服务 X.509 证书的信息。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-120">The behavior specifies the service credentials that are to be used for client authentication and also information about the service X.509 certificate.</span></span>

```csharp
public static class BindingHelper
{
    public static Binding CreateCreditCardBinding()
    {
        HttpTransportBindingElement httpTransport = new HttpTransportBindingElement();

        // The message security binding element will be configured to require a credit card.
        // The token that is encrypted with the service's certificate.
        SymmetricSecurityBindingElement messageSecurity = new SymmetricSecurityBindingElement();
        messageSecurity.EndpointSupportingTokenParameters.SignedEncrypted.Add(new CreditCardTokenParameters());
        X509SecurityTokenParameters x509ProtectionParameters = new X509SecurityTokenParameters();
        x509ProtectionParameters.InclusionMode = SecurityTokenInclusionMode.Never;
        messageSecurity.ProtectionTokenParameters = x509ProtectionParameters;
        return new CustomBinding(messageSecurity, httpTransport);
    }
}
```

 <span data-ttu-id="4d5ee-121">为了使用消息中的信用卡令牌，此示例使用自定义服务凭据来提供此功能。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-121">To consume a credit card token in the message, the sample uses custom service credentials to provide this functionality.</span></span> <span data-ttu-id="4d5ee-122">服务凭据类位于 `CreditCardServiceCredentials` 类中，并使用 `EchoServiceHost.InitializeRuntime` 方法添加到服务主机的行为集合中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-122">The service credentials class is located in the `CreditCardServiceCredentials` class and is added to the behaviors collections of the service host in the `EchoServiceHost.InitializeRuntime` method.</span></span>

```csharp
class EchoServiceHost : ServiceHost
{
    string creditCardFile;

    public EchoServiceHost(parameters Uri[] addresses)
        : base(typeof(EchoService), addresses)
    {
        creditCardFile = ConfigurationManager.AppSettings["creditCardFile"];
        if (string.IsNullOrEmpty(creditCardFile))
        {
            throw new ConfigurationErrorsException("creditCardFile not specified in service config");
        }

        creditCardFile = String.Format("{0}\\{1}", System.Web.Hosting.HostingEnvironment.ApplicationPhysicalPath, creditCardFile);
    }

    override protected void InitializeRuntime()
    {
        // Create a credit card service credentials and add it to the behaviors.
        CreditCardServiceCredentials serviceCredentials = new CreditCardServiceCredentials(this.creditCardFile);
        serviceCredentials.ServiceCertificate.SetCertificate("CN=localhost", StoreLocation.LocalMachine, StoreName.My);
        this.Description.Behaviors.Remove((typeof(ServiceCredentials)));
        this.Description.Behaviors.Add(serviceCredentials);

        // Register a credit card binding for the endpoint.
        Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
        this.AddServiceEndpoint(typeof(IEchoService), creditCardBinding, string.Empty);

        base.InitializeRuntime();
    }
}
```

 <span data-ttu-id="4d5ee-123">客户端终结点的配置方式与服务终结点类似。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-123">The client endpoint is configured in a similar manner as the service endpoint.</span></span> <span data-ttu-id="4d5ee-124">客户端使用相同的 `BindingHelper` 类创建绑定。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-124">The client uses the same `BindingHelper` class to create a binding.</span></span> <span data-ttu-id="4d5ee-125">设置的其余部分位于 `Client` 类中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-125">The rest of the setup is located in the `Client` class.</span></span> <span data-ttu-id="4d5ee-126">客户端还通过向客户端终结点行为集合添加具有适当数据的 `CreditCardToken` 实例来设置要包含在 `CreditCardClientCredentials` 中的信息和有关在设置代码中的服务 X.509 证书的信息。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-126">The client also sets information to be contained in the `CreditCardToken` and information about the service X.509 certificate in the setup code by adding a `CreditCardClientCredentials` instance with the proper data to the client endpoint behaviors collection.</span></span> <span data-ttu-id="4d5ee-127">此实例使用将主题名称设置为 `CN=localhost` 的 X.509 证书作为服务证书。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-127">The sample uses X.509 certificate with subject name set to `CN=localhost` as the service certificate.</span></span>

```csharp
Binding creditCardBinding = BindingHelper.CreateCreditCardBinding();
EndpointAddress serviceAddress = new EndpointAddress("http://localhost/servicemodelsamples/service.svc");

// Create a client with given client endpoint configuration
channelFactory = new ChannelFactory<IEchoService>(creditCardBinding, serviceAddress);

// configure the credit card credentials on the channel factory
CreditCardClientCredentials credentials =
      new CreditCardClientCredentials(
      new CreditCardInfo(creditCardNumber, issuer, expirationTime));
// configure the service certificate on the credentials
credentials.ServiceCertificate.SetDefaultCertificate(
      "CN=localhost", StoreLocation.LocalMachine, StoreName.My);

// replace ClientCredentials with CreditCardClientCredentials
channelFactory.Endpoint.Behaviors.Remove(typeof(ClientCredentials));
channelFactory.Endpoint.Behaviors.Add(credentials);

client = channelFactory.CreateChannel();

Console.WriteLine("Echo service returned: {0}", client.Echo());

((IChannel)client).Close();
channelFactory.Close();
```

## <a name="custom-security-token-implementation"></a><span data-ttu-id="4d5ee-128">自定义安全令牌实现</span><span class="sxs-lookup"><span data-stu-id="4d5ee-128">Custom Security Token Implementation</span></span>
 <span data-ttu-id="4d5ee-129">若要启用 WCF 中的自定义安全令牌，请创建自定义安全令牌的对象表示形式。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-129">To enable a custom security token in WCF, create an object representation of the custom security token.</span></span> <span data-ttu-id="4d5ee-130">此示例的 `CreditCardToken` 类中有此表示形式。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-130">The sample has this representation in the `CreditCardToken` class.</span></span> <span data-ttu-id="4d5ee-131">对象表示形式负责保存所有相关的安全令牌信息并负责提供包含在安全令牌中的安全密钥列表。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-131">The object representation is responsible for holding all relevant security token information and to provide a list of security keys contained in the security token.</span></span> <span data-ttu-id="4d5ee-132">在本例中，信用卡安全令牌不包含任何安全密钥。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-132">In this case, the credit card security token does not contain any security key.</span></span>

 <span data-ttu-id="4d5ee-133">下一节介绍必须做可使得在通过网络传输的自定义令牌和使用 WCF 终结点的内容。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-133">The next section describes what must be done to enable a custom token to be transmitted over the wire and consumed by a WCF endpoint.</span></span>

```csharp
class CreditCardToken : SecurityToken
{
    CreditCardInfo cardInfo;
    DateTime effectiveTime = DateTime.UtcNow;
    string id;
    ReadOnlyCollection<SecurityKey> securityKeys;

    public CreditCardToken(CreditCardInfo cardInfo) : this(cardInfo, Guid.NewGuid().ToString()) { }

    public CreditCardToken(CreditCardInfo cardInfo, string id)
    {
        if (cardInfo == null)
            throw new ArgumentNullException("cardInfo");

        if (id == null)
            throw new ArgumentNullException("id");

        this.cardInfo = cardInfo;
        this.id = id;

        // The credit card token is not capable of any cryptography.
        this.securityKeys = new ReadOnlyCollection<SecurityKey>(new List<SecurityKey>());
    }

    public CreditCardInfo CardInfo { get { return this.cardInfo; } }

    public override ReadOnlyCollection<SecurityKey> SecurityKeys { get { return this.securityKeys; } }

    public override DateTime ValidFrom { get { return this.effectiveTime; } }
    public override DateTime ValidTo { get { return this.cardInfo.ExpirationDate; } }
    public override string Id { get { return this.id; } }
}
```

## <a name="getting-the-custom-credit-card-token-to-and-from-the-message"></a><span data-ttu-id="4d5ee-134">向消息中写入和从消息中获取自定义信用卡令牌</span><span class="sxs-lookup"><span data-stu-id="4d5ee-134">Getting the Custom Credit Card Token to and from the Message</span></span>
 <span data-ttu-id="4d5ee-135">安全令牌序列化程序在 WCF 负责从消息中的 XML 创建安全令牌的对象表示形式和创建 XML 形式的安全令牌。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-135">Security token serializers in WCF are responsible for creating an object representation of security tokens from the XML in the message and creating a XML form of the security tokens.</span></span> <span data-ttu-id="4d5ee-136">安全令牌序列化程序还负责其他功能，如读取和写入指向安全令牌的密钥标识符，但本示例只使用与安全令牌相关的功能。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-136">They are also responsible for other functionality such as reading and writing key identifiers pointing to security tokens, but this example uses only security token-related functionality.</span></span> <span data-ttu-id="4d5ee-137">要启用自定义令牌，您必须实现您自己的安全令牌序列化程序。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-137">To enable a custom token you must implement your own security token serializer.</span></span> <span data-ttu-id="4d5ee-138">本示例使用 `CreditCardSecurityTokenSerializer` 类来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-138">This sample uses the `CreditCardSecurityTokenSerializer` class for this purpose.</span></span>

 <span data-ttu-id="4d5ee-139">在服务上，自定义序列化程序读取 XML 形式的自定义令牌并据此创建自定义令牌的对象表示形式。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-139">On the service, the custom serializer reads the XML form of the custom token and creates the custom token object representation from it.</span></span>

 <span data-ttu-id="4d5ee-140">在客户端上，`CreditCardSecurityTokenSerializer` 类将包含在安全令牌对象表示形式中的信息写入到 XML 编写器中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-140">On the client, the `CreditCardSecurityTokenSerializer` class writes the information contained in the security token object representation into the XML writer.</span></span>

```csharp
public class CreditCardSecurityTokenSerializer : WSSecurityTokenSerializer
{
    public CreditCardSecurityTokenSerializer(SecurityTokenVersion version) : base() { }

    protected override bool CanReadTokenCore(XmlReader reader)
    {
        XmlDictionaryReader localReader = XmlDictionaryReader.CreateDictionaryReader(reader);

        if (reader == null) throw new ArgumentNullException("reader");

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
            return true;

        return base.CanReadTokenCore(reader);
    }

    protected override SecurityToken ReadTokenCore(XmlReader reader, SecurityTokenResolver tokenResolver)
    {
        if (reader == null) throw new ArgumentNullException("reader");

        if (reader.IsStartElement(Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace))
        {
            string id = reader.GetAttribute(Constants.Id, Constants.WsUtilityNamespace);

            reader.ReadStartElement();

            // Read the credit card number.
            string creditCardNumber = reader.ReadElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace);

            // Read the expiration date.
            string expirationTimeString = reader.ReadElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace);
            DateTime expirationTime = XmlConvert.ToDateTime(expirationTimeString, XmlDateTimeSerializationMode.Utc);

            // Read the issuer of the credit card.
            string creditCardIssuer = reader.ReadElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace);
            reader.ReadEndElement();

            CreditCardInfo cardInfo = new CreditCardInfo(creditCardNumber, creditCardIssuer, expirationTime);

            return new CreditCardToken(cardInfo, id);
        }
        else
        {
            return WSSecurityTokenSerializer.DefaultInstance.ReadToken(reader, tokenResolver);
        }
    }

    protected override bool CanWriteTokenCore(SecurityToken token)
    {
        if (token is CreditCardToken)
            return true;

        else
            return base.CanWriteTokenCore(token);
    }

    protected override void WriteTokenCore(XmlWriter writer, SecurityToken token)
    {
        if (writer == null) { throw new ArgumentNullException("writer"); }
        if (token == null) { throw new ArgumentNullException("token"); }

        CreditCardToken c = token as CreditCardToken;
        if (c != null)
        {
            writer.WriteStartElement(Constants.CreditCardTokenPrefix, Constants.CreditCardTokenName, Constants.CreditCardTokenNamespace);
            writer.WriteAttributeString(Constants.WsUtilityPrefix, Constants.Id, Constants.WsUtilityNamespace, token.Id);
            writer.WriteElementString(Constants.CreditCardNumberElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardNumber);
            writer.WriteElementString(Constants.CreditCardExpirationElementName, Constants.CreditCardTokenNamespace, XmlConvert.ToString(c.CardInfo.ExpirationDate, XmlDateTimeSerializationMode.Utc));
            writer.WriteElementString(Constants.CreditCardIssuerElementName, Constants.CreditCardTokenNamespace, c.CardInfo.CardIssuer);
            writer.WriteEndElement();
            writer.Flush();
        }
        else
        {
            base.WriteTokenCore(writer, token);
        }
    }
}
```

## <a name="how-token-provider-and-token-authenticator-classes-are-created"></a><span data-ttu-id="4d5ee-141">如何创建令牌提供程序和令牌身份验证器类</span><span class="sxs-lookup"><span data-stu-id="4d5ee-141">How Token Provider and Token Authenticator Classes are Created</span></span>
 <span data-ttu-id="4d5ee-142">客户端和服务凭据负责提供安全令牌管理器实例。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-142">Client and service credentials are responsible for providing the security token manager instance.</span></span> <span data-ttu-id="4d5ee-143">安全令牌管理器实例用于获取令牌提供程序、令牌身份验证器和令牌序列化程序。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-143">The security token manager instance is used to get token providers, token authenticators and token serializers.</span></span>

 <span data-ttu-id="4d5ee-144">令牌提供程序会基于包含在客户端或服务凭据中的信息创建令牌的对象表示形式。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-144">The token provider creates an object representation of the token based on the information contained in the client or service credentials.</span></span> <span data-ttu-id="4d5ee-145">然后使用令牌序列化程序（在上一节中讨论）将令牌对象表示形式写入消息。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-145">The token object representation is then written to the message using the token serializer (discussed in the previous section).</span></span>

 <span data-ttu-id="4d5ee-146">令牌身份验证器验证在消息中到达的令牌。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-146">The token authenticator validates tokens that arrive in the message.</span></span> <span data-ttu-id="4d5ee-147">通过令牌序列化程序创建传入令牌的对象表示形式。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-147">The incoming token object representation is created by the token serializer.</span></span> <span data-ttu-id="4d5ee-148">然后将此对象表示形式传递给身份验证器进行验证。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-148">This object representation is then passed to the token authenticator for validation.</span></span> <span data-ttu-id="4d5ee-149">在成功验证令牌后，令牌身份验证器会返回 `IAuthorizationPolicy` 对象的集合，这些对象表示包含在令牌中的信息。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-149">After the token is successfully validated, the token authenticator returns a collection of `IAuthorizationPolicy` objects that represent the information contained in the token.</span></span> <span data-ttu-id="4d5ee-150">在稍后处理消息的过程中将使用此信息来执行身份验证决定并为应用程序提供声明。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-150">This information is used later during the message processing to perform authorization decisions and to provide claims for the application.</span></span> <span data-ttu-id="4d5ee-151">在本示例中，信用卡令牌身份验证器使用 `CreditCardTokenAuthorizationPolicy` 来实现此目的。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-151">In this example, the credit card token authenticator uses `CreditCardTokenAuthorizationPolicy` for this purpose.</span></span>

 <span data-ttu-id="4d5ee-152">令牌序列化程序负责通过网络获取令牌的对象表示形式。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-152">The token serializer is responsible for getting the object representation of the token to and from the wire.</span></span> <span data-ttu-id="4d5ee-153">此过程在上一节中进行讨论。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-153">This is discussed in the previous section.</span></span>

 <span data-ttu-id="4d5ee-154">在本示例中，由于只想在客户端到服务方向传输信用卡令牌，因此只在客户端上使用令牌提供程序并只在服务上使用令牌身份验证器。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-154">In this sample, we use a token provider only on the client and a token authenticator only on the service, because we want to transmit a credit card token only in the client-to-service direction.</span></span>

 <span data-ttu-id="4d5ee-155">在客户端上，此功能位于 `CreditCardClientCrendentials`、`CreditCardClientCredentialsSecurityTokenManager` 和 `CreditCardTokenProvider` 类中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-155">The functionality on the client is located in the `CreditCardClientCrendentials`, `CreditCardClientCredentialsSecurityTokenManager` and `CreditCardTokenProvider` classes.</span></span>

 <span data-ttu-id="4d5ee-156">在服务上，此功能位于 `CreditCardServiceCredentials`、`CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` 和 `CreditCardTokenAuthorizationPolicy` 类中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-156">On the service, the functionality resides in the `CreditCardServiceCredentials`, `CreditCardServiceCredentialsSecurityTokenManager`, `CreditCardTokenAuthenticator` and `CreditCardTokenAuthorizationPolicy` classes.</span></span>

```csharp
    public class CreditCardClientCredentials : ClientCredentials
    {
        CreditCardInfo creditCardInfo;

        public CreditCardClientCredentials(CreditCardInfo creditCardInfo)
            : base()
        {
            if (creditCardInfo == null)
                throw new ArgumentNullException("creditCardInfo");

            this.creditCardInfo = creditCardInfo;
        }

        public CreditCardInfo CreditCardInfo
        {
            get { return this.creditCardInfo; }
        }

        protected override ClientCredentials CloneCore()
        {
            return new CreditCardClientCredentials(this.creditCardInfo);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardClientCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardClientCredentialsSecurityTokenManager : ClientCredentialsSecurityTokenManager
    {
        CreditCardClientCredentials creditCardClientCredentials;

        public CreditCardClientCredentialsSecurityTokenManager(CreditCardClientCredentials creditCardClientCredentials)
            : base (creditCardClientCredentials)
        {
            this.creditCardClientCredentials = creditCardClientCredentials;
        }

        public override SecurityTokenProvider CreateSecurityTokenProvider(SecurityTokenRequirement tokenRequirement)
        {
            // handle this token for Custom
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
                return new CreditCardTokenProvider(this.creditCardClientCredentials.CreditCardInfo);
            // return server cert
            else if (tokenRequirement is InitiatorServiceModelSecurityTokenRequirement)
            {
                if (tokenRequirement.TokenType == SecurityTokenTypes.X509Certificate)
                {
                    return new X509SecurityTokenProvider(creditCardClientCredentials.ServiceCertificate.DefaultCertificate);
                }
            }

            return base.CreateSecurityTokenProvider(tokenRequirement);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {

            return new CreditCardSecurityTokenSerializer(version);
        }

    }

    class CreditCardTokenProvider : SecurityTokenProvider
    {
        CreditCardInfo creditCardInfo;

        public CreditCardTokenProvider(CreditCardInfo creditCardInfo) : base()
        {
            if (creditCardInfo == null)
            {
                throw new ArgumentNullException("creditCardInfo");
            }
            this.creditCardInfo = creditCardInfo;
        }

        protected override SecurityToken GetTokenCore(TimeSpan timeout)
        {
            SecurityToken result = new CreditCardToken(this.creditCardInfo);
            return result;
        }
    }

    public class CreditCardServiceCredentials : ServiceCredentials
    {
        string creditCardFile;

        public CreditCardServiceCredentials(string creditCardFile)
            : base()
        {
            if (creditCardFile == null)
                throw new ArgumentNullException("creditCardFile");

            this.creditCardFile = creditCardFile;
        }

        public string CreditCardDataFile
        {
            get { return this.creditCardFile; }
        }

        protected override ServiceCredentials CloneCore()
        {
            return new CreditCardServiceCredentials(this.creditCardFile);
        }

        public override SecurityTokenManager CreateSecurityTokenManager()
        {
            return new CreditCardServiceCredentialsSecurityTokenManager(this);
        }
    }

    public class CreditCardServiceCredentialsSecurityTokenManager : ServiceCredentialsSecurityTokenManager
    {
        CreditCardServiceCredentials creditCardServiceCredentials;

        public CreditCardServiceCredentialsSecurityTokenManager(CreditCardServiceCredentials creditCardServiceCredentials)
            : base(creditCardServiceCredentials)
        {
            this.creditCardServiceCredentials = creditCardServiceCredentials;
        }

        public override SecurityTokenAuthenticator CreateSecurityTokenAuthenticator(SecurityTokenRequirement tokenRequirement, out SecurityTokenResolver outOfBandTokenResolver)
        {
            if (tokenRequirement.TokenType == Constants.CreditCardTokenType)
            {
                outOfBandTokenResolver = null;
                return new CreditCardTokenAuthenticator(creditCardServiceCredentials.CreditCardDataFile);
            }

            return base.CreateSecurityTokenAuthenticator(tokenRequirement, out outOfBandTokenResolver);
        }

        public override SecurityTokenSerializer CreateSecurityTokenSerializer(SecurityTokenVersion version)
        {
            return new CreditCardSecurityTokenSerializer(version);
        }
    }

    class CreditCardTokenAuthenticator : SecurityTokenAuthenticator
    {
        string creditCardsFile;
        public CreditCardTokenAuthenticator(string creditCardsFile)
        {
            this.creditCardsFile = creditCardsFile;
        }

        protected override bool CanValidateTokenCore(SecurityToken token)
        {
            return (token is CreditCardToken);
        }

        protected override ReadOnlyCollection<IAuthorizationPolicy> ValidateTokenCore(SecurityToken token)
        {
            CreditCardToken creditCardToken = token as CreditCardToken;

            if (creditCardToken.CardInfo.ExpirationDate < DateTime.UtcNow)
                throw new SecurityTokenValidationException("The credit card has expired");
            if (!IsCardNumberAndExpirationValid(creditCardToken.CardInfo))
                throw new SecurityTokenValidationException("Unknown or invalid credit card");

            // the credit card token has only 1 claim - the card number. The issuer for the claim is the
            // credit card issuer

            DefaultClaimSet cardIssuerClaimSet = new DefaultClaimSet(new Claim(ClaimTypes.Name, creditCardToken.CardInfo.CardIssuer, Rights.PossessProperty));
            DefaultClaimSet cardClaimSet = new DefaultClaimSet(cardIssuerClaimSet, new Claim(Constants.CreditCardNumberClaim, creditCardToken.CardInfo.CardNumber, Rights.PossessProperty));
            List<IAuthorizationPolicy> policies = new List<IAuthorizationPolicy>(1);
            policies.Add(new CreditCardTokenAuthorizationPolicy(cardClaimSet));
            return policies.AsReadOnly();
        }

        /// <summary>
        /// Helper method to check if a given credit card entry is present in the User DB
        /// </summary>
        private bool IsCardNumberAndExpirationValid(CreditCardInfo cardInfo)
        {
            try
            {
                using (StreamReader myStreamReader = new StreamReader(this.creditCardsFile))
                {
                    string line = "";
                    while ((line = myStreamReader.ReadLine()) != null)
                    {
                        string[] splitEntry = line.Split('#');
                        if (splitEntry[0] == cardInfo.CardNumber)
                        {
                            string expirationDateString = splitEntry[1].Trim();
                            DateTime expirationDateOnFile = DateTime.Parse(expirationDateString, System.Globalization.DateTimeFormatInfo.InvariantInfo, System.Globalization.DateTimeStyles.AdjustToUniversal);
                            if (cardInfo.ExpirationDate == expirationDateOnFile)
                            {
                                string issuer = splitEntry[2];
                                return issuer.Equals(cardInfo.CardIssuer, StringComparison.InvariantCultureIgnoreCase);
                            }
                            else
                            {
                                return false;
                            }
                        }
                    }
                    return false;
                }
            }
            catch (Exception e)
            {
                throw new Exception("BookStoreService: Error while retrieving credit card information from User DB " + e.ToString());
            }
        }
    }

    public class CreditCardTokenAuthorizationPolicy : IAuthorizationPolicy
    {
        string id;
        ClaimSet issuer;
        IEnumerable<ClaimSet> issuedClaimSets;

        public CreditCardTokenAuthorizationPolicy(ClaimSet issuedClaims)
        {
            if (issuedClaims == null)
                throw new ArgumentNullException("issuedClaims");
            this.issuer = issuedClaims.Issuer;
            this.issuedClaimSets = new ClaimSet[] { issuedClaims };
            this.id = Guid.NewGuid().ToString();
        }

        public ClaimSet Issuer { get { return this.issuer; } }

        public string Id { get { return this.id; } }

        public bool Evaluate(EvaluationContext context, ref object state)
        {
            foreach (ClaimSet issuance in this.issuedClaimSets)
            {
                context.AddClaimSet(this, issuance);
            }

            return true;
        }
    }
```

## <a name="displaying-the-callers-information"></a><span data-ttu-id="4d5ee-157">显示调用方信息</span><span class="sxs-lookup"><span data-stu-id="4d5ee-157">Displaying the Callers' Information</span></span>
 <span data-ttu-id="4d5ee-158">若要显示调用方信息，请使用 `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets`，如下面的示例代码所示。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-158">To display the caller's information, use the `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` as shown in the following sample code.</span></span> <span data-ttu-id="4d5ee-159">`ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` 包含与当前调用方关联的授权声明。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-159">The `ServiceSecurityContext.Current.AuthorizationContext.ClaimSets` contains authorization claims associated with the current caller.</span></span> <span data-ttu-id="4d5ee-160">声明由 `CreditCardToken` 类在其 `AuthorizationPolicies` 集合中提供。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-160">The claims are supplied by the `CreditCardToken` class in its `AuthorizationPolicies` collection.</span></span>

```csharp
bool TryGetStringClaimValue(ClaimSet claimSet, string claimType, out string claimValue)
{
    claimValue = null;
    IEnumerable<Claim> matchingClaims = claimSet.FindClaims(claimType, Rights.PossessProperty);
    if (matchingClaims == null)
        return false;
    IEnumerator<Claim> enumerator = matchingClaims.GetEnumerator();
    enumerator.MoveNext();
    claimValue = (enumerator.Current.Resource == null) ? null :
        enumerator.Current.Resource.ToString();
    return true;
}

string GetCallerCreditCardNumber()
{
     foreach (ClaimSet claimSet in
         ServiceSecurityContext.Current.AuthorizationContext.ClaimSets)
     {
         string creditCardNumber = null;
         if (TryGetStringClaimValue(claimSet,
             Constants.CreditCardNumberClaim, out creditCardNumber))
             {
                 string issuer;
                 if (!TryGetStringClaimValue(claimSet.Issuer,
                        ClaimTypes.Name, out issuer))
                 {
                     issuer = "Unknown";
                 }
                 return $"Credit card '{creditCardNumber}' issued by '{issuer}'";
        }
    }
    return "Credit card is not known";
}
```

 <span data-ttu-id="4d5ee-161">运行示例时，操作请求和响应将显示在客户端控制台窗口中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-161">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="4d5ee-162">在客户端窗口中按 Enter 可以关闭客户端。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-162">Press ENTER in the client window to shut down the client.</span></span>

## <a name="setup-batch-file"></a><span data-ttu-id="4d5ee-163">设置批处理文件</span><span class="sxs-lookup"><span data-stu-id="4d5ee-163">Setup Batch File</span></span>
 <span data-ttu-id="4d5ee-164">通过运行此示例随附的 Setup.bat 批处理文件，可以用相关的证书将服务器配置为运行需要基于服务器证书的安全性的 IIS 承载的应用程序。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-164">The Setup.bat batch file included with this sample allows you to configure the server with relevant certificates to run the IIS-hosted application that requires server certificate-based security.</span></span> <span data-ttu-id="4d5ee-165">必须修改此批处理文件，以便跨计算机或在非承载情况下工作。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-165">This batch file must be modified to work across computers or to work in a non-hosted case.</span></span>

 <span data-ttu-id="4d5ee-166">下面提供了批处理文件不同节的简要概述，以便可以修改批处理文件从而在相应的配置中运行。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-166">The following provides a brief overview of the different sections of the batch files so that they can be modified to run in the appropriate configuration.</span></span>

-   <span data-ttu-id="4d5ee-167">创建服务器证书：</span><span class="sxs-lookup"><span data-stu-id="4d5ee-167">Creating the server certificate:</span></span>

     <span data-ttu-id="4d5ee-168">`Setup.bat` 批处理文件中的以下行创建将要使用的服务器证书。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-168">The following lines from the `Setup.bat` batch file create the server certificate to be used.</span></span> <span data-ttu-id="4d5ee-169">`%SERVER_NAME%`变量指定服务器名称。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-169">The `%SERVER_NAME%` variable specifies the server name.</span></span> <span data-ttu-id="4d5ee-170">更改此变量可以指定您自己的服务器名称。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-170">Change this variable to specify your own server name.</span></span> <span data-ttu-id="4d5ee-171">此批处理文件中的默认值为 localhost。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-171">The default in this batch file is localhost.</span></span> <span data-ttu-id="4d5ee-172">如果更改 `%SERVER_NAME%` 变量，则必须浏览 Client.cs 和 Service.cs 文件并用 Setup.bat 脚本中使用的服务器名来替换 localhost 的所有实例。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-172">If you change the `%SERVER_NAME%` variable, you must go through the Client.cs and Service.cs files and replace all instances of localhost with the server name that you use in the Setup.bat script.</span></span>

     <span data-ttu-id="4d5ee-173">证书存储在 `LocalMachine` 存储位置下的 My（个人）存储区中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-173">The certificate is stored in My (Personal) store under the `LocalMachine` store location.</span></span> <span data-ttu-id="4d5ee-174">对于 IIS 承载的服务，证书存储在 LocalMachine 存储区中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-174">The certificate is stored in the LocalMachine store for the IIS-hosted services.</span></span> <span data-ttu-id="4d5ee-175">对于自承载服务，应该通过用 CurrentUser 替换字符串 LocalMachine 来修改批处理文件，以便将客户端证书存储在 CurrentUser 存储位置。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-175">For self-hosted services, you should modify the batch file to store the client certificate in the CurrentUser store location by replacing the string LocalMachine with CurrentUser.</span></span>

    ```
    echo ************
    echo Server cert setup starting
    echo %SERVER_NAME%
    echo ************
    echo making server cert
    echo ************
    makecert.exe -sr LocalMachine -ss MY -a sha1 -n CN=%SERVER_NAME% -sky exchange -pe
    ```

-   <span data-ttu-id="4d5ee-176">将服务器证书安装到客户端的受信任证书存储区中：</span><span class="sxs-lookup"><span data-stu-id="4d5ee-176">Installing the server certificate into client's trusted certificate store:</span></span>

     <span data-ttu-id="4d5ee-177">Setup.bat 批处理文件中的以下行将服务器证书复制到客户端的受信任的人的存储区中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-177">The following lines in the Setup.bat batch file copy the server certificate into the client trusted people store.</span></span> <span data-ttu-id="4d5ee-178">因为客户端系统不隐式信任 Makecert.exe 生成的证书，所以需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-178">This step is required because certificates generated by Makecert.exe are not implicitly trusted by the client system.</span></span> <span data-ttu-id="4d5ee-179">如果您已经拥有一个证书，该证书来源于客户端的受信任根证书（例如由 Microsoft 颁发的证书），则不需要执行使用服务器证书填充客户端证书存储区这一步骤。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-179">If you already have a certificate that is rooted in a client trusted root certificate—for example, a Microsoft issued certificate—this step of populating the client certificate store with the server certificate is not required.</span></span>

    ```
    echo ************
    echo copying server cert to client's TrustedPeople store
    echo ************
    certmgr.exe -add -r LocalMachine -s My -c -n %SERVER_NAME% -r CurrentUser -s TrustedPeople
    ```

-   <span data-ttu-id="4d5ee-180">若要从 IIS 承载的服务启用对证书私钥的访问，必须为 IIS 承载的进程运行时所使用的用户帐户授予对该私钥的适当权限。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-180">To enable access to the certificate private key from the IIS-hosted service, the user account under which the IIS-hosted process is running must be granted appropriate permissions for the private key.</span></span> <span data-ttu-id="4d5ee-181">这将由 Setup.bat 脚本中的最后步骤来完成。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-181">This is accomplished by last steps in the Setup.bat script.</span></span>

    ```
    echo ************
    echo setting privileges on server certificates
    echo ************
    for /F "delims=" %%i in ('"%ProgramFiles%\ServiceModelSampleTools\FindPrivateKey.exe" My LocalMachine -n CN^=%SERVER_NAME% -a') do set PRIVATE_KEY_FILE=%%i
    set WP_ACCOUNT=NT AUTHORITY\NETWORK SERVICE
    (ver | findstr /C:"5.1") && set WP_ACCOUNT=%COMPUTERNAME%\ASPNET
    echo Y|cacls.exe "%PRIVATE_KEY_FILE%" /E /G "%WP_ACCOUNT%":R
    iisreset
    ```

> [!NOTE]
>  <span data-ttu-id="4d5ee-182">Setup.bat 批处理文件旨在为从 Visual Studio 2012 命令提示运行。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-182">The Setup.bat batch file is designed to be run from a Visual Studio 2012 Command Prompt.</span></span> <span data-ttu-id="4d5ee-183">在 Visual Studio 2012 命令提示符点设置为包含 Setup.bat 脚本所需的可执行文件的目录路径环境变量。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-183">The PATH environment variable set within the Visual Studio 2012 Command Prompt points to the directory that contains executables required by the Setup.bat script.</span></span>

#### <a name="to-set-up-and-build-the-sample"></a><span data-ttu-id="4d5ee-184">设置和生成示例</span><span class="sxs-lookup"><span data-stu-id="4d5ee-184">To set up and build the sample</span></span>

1.  <span data-ttu-id="4d5ee-185">请确保您具有执行[的 Windows Communication Foundation 示例的一次性安装过程](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-185">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2.  <span data-ttu-id="4d5ee-186">若要生成解决方案，请按照中的说明[生成 Windows Communication Foundation 示例](../../../../docs/framework/wcf/samples/building-the-samples.md)。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-186">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

#### <a name="to-run-the-sample-on-the-same-computer"></a><span data-ttu-id="4d5ee-187">在同一计算机上运行示例</span><span class="sxs-lookup"><span data-stu-id="4d5ee-187">To run the sample on the same computer</span></span>

1.  <span data-ttu-id="4d5ee-188">使用管理员特权打开 Visual Studio 2012 命令提示符窗口并从示例安装文件夹运行 Setup.bat。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-188">Open a Visual Studio 2012 Command Prompt window with administrator privileges and run Setup.bat from the sample install folder.</span></span> <span data-ttu-id="4d5ee-189">这将安装运行示例所需的所有证书。请确保路径包括 Makecert.exe 所在的文件夹。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-189">This installs all the certificates required for running the sample.Make sure that the path includes the folder where Makecert.exe is located.</span></span>

> [!NOTE]
>  <span data-ttu-id="4d5ee-190">确保在运行完该示例后运行 Cleanup.bat 移除证书。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-190">Be sure to remove the certificates by running Cleanup.bat when finished with the sample.</span></span> <span data-ttu-id="4d5ee-191">其他安全示例使用相同的证书。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-191">Other security samples use the same certificates.</span></span>  
  
1.  <span data-ttu-id="4d5ee-192">从 client\bin 目录启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-192">Launch Client.exe from client\bin directory.</span></span> <span data-ttu-id="4d5ee-193">客户端活动将显示在客户端控制台应用程序上。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-193">Client activity is displayed on the client console application.</span></span>  
  
2.  <span data-ttu-id="4d5ee-194">如果客户端与服务无法进行通信，请参见 [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-194">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-run-the-sample-across-computer"></a><span data-ttu-id="4d5ee-195">跨计算机运行示例</span><span class="sxs-lookup"><span data-stu-id="4d5ee-195">To run the sample across computer</span></span>  
  
1.  <span data-ttu-id="4d5ee-196">在服务计算机上为服务二进制文件创建一个目录。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-196">Create a directory on the service computer for the service binaries.</span></span>  
  
2.  <span data-ttu-id="4d5ee-197">将服务程序文件复制到服务计算机上的服务目录。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-197">Copy the service program files into the service directory on the service computer.</span></span> <span data-ttu-id="4d5ee-198">不要忘记复制 CreditCardFile.txt，否则信用卡身份验证器将不能验证从客户端发送的信用卡信息。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-198">Do not forget to copy CreditCardFile.txt; otherwise the credit card authenticator cannot validate credit card information sent from the client.</span></span> <span data-ttu-id="4d5ee-199">另外，将 Setup.bat 和 Cleanup.bat 文件复制到服务计算机上。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-199">Also copy the Setup.bat and Cleanup.bat files to the service computer.</span></span>  
  
3.  <span data-ttu-id="4d5ee-200">必须具有一个其主题名称中包含计算机的完全限定域名的服务器证书。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-200">You must have a server certificate with the subject name that contains the fully-qualified domain name of the computer.</span></span> <span data-ttu-id="4d5ee-201">如果您将 `%SERVER_NAME%` 变量更改为承载服务的计算机的完全限定的名称，您可以使用 Setup.bat 来创建一个这样的证书。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-201">You can create one using the Setup.bat if you change the `%SERVER_NAME%` variable to fully-qualified name of the computer where the service is hosted.</span></span> <span data-ttu-id="4d5ee-202">请注意，必须在使用管理员特权打开的 Visual Studio 命令提示中运行 Setup.bat 文件。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-202">Note that the Setup.bat file must be run in a Visual Studio command prompt opened with administrator privileges.</span></span>  
  
4.  <span data-ttu-id="4d5ee-203">将服务器证书复制到客户端上的 CurrentUser-TrustedPeople 存储区中。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-203">Copy the server certificate into the CurrentUser-TrustedPeople store on the client.</span></span> <span data-ttu-id="4d5ee-204">只有当服务器证书不是由受信任的颁发者颁发的情况下才需要执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-204">You must do this only if the server certificate is not issued by a trusted issuer.</span></span>  
  
5.  <span data-ttu-id="4d5ee-205">在 EchoServiceHost.cs 文件中，更改证书主题名称的值以指定一个完全限定的计算机名，而不是 localhost。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-205">In the EchoServiceHost.cs file, change the value of the certificate subject name to specify a fully-qualified computer name instead of localhost.</span></span>  
  
6.  <span data-ttu-id="4d5ee-206">将 \client\bin\ 文件夹（在语言特定文件夹内）中的客户端程序文件复制到客户端计算机上。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-206">Copy the client program files from the \client\bin\ folder, under the language-specific folder, to the client computer.</span></span>  
  
7.  <span data-ttu-id="4d5ee-207">在 Client.cs 文件中，更改终结点的地址值以与服务的新地址相匹配。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-207">In the Client.cs file, change the address value of the endpoint to match the new address of your service.</span></span>  
  
8.  <span data-ttu-id="4d5ee-208">在 Client.cs 文件中，更改服务 X.509 证书的主题名称以与远程主机的完全限定的计算机名（而不是 localhost）相匹配。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-208">In the Client.cs file change the subject name of the service X.509 certificate to match the fully-qualified computer name of the remote host instead of localhost.</span></span>  
  
9. <span data-ttu-id="4d5ee-209">在客户端计算机上，从命令提示窗口中启动 Client.exe。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-209">On the client computer, launch Client.exe from a command prompt window.</span></span>  
  
10. <span data-ttu-id="4d5ee-210">如果客户端与服务无法进行通信，请参见 [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b)。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-210">If the client and service are not able to communicate, see [Troubleshooting Tips](https://msdn.microsoft.com/library/8787c877-5e96-42da-8214-fa737a38f10b).</span></span>  
  
#### <a name="to-clean-up-after-the-sample"></a><span data-ttu-id="4d5ee-211">运行示例后进行清理</span><span class="sxs-lookup"><span data-stu-id="4d5ee-211">To clean up after the sample</span></span>  
  
1.  <span data-ttu-id="4d5ee-212">运行完示例后运行示例文件夹中的 Cleanup.bat。</span><span class="sxs-lookup"><span data-stu-id="4d5ee-212">Run Cleanup.bat in the samples folder once you have finished running the sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d5ee-213">请参阅</span><span class="sxs-lookup"><span data-stu-id="4d5ee-213">See Also</span></span>
