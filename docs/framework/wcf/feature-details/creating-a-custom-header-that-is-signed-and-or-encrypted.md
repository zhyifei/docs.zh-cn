---
title: 创建自定义标头进行签名和-或加密
ms.date: 03/30/2017
ms.assetid: e8668b37-c79f-4714-9de5-afcb88b9ff02
ms.openlocfilehash: 0f8f86bcb5494cd502d14aff1cf3c4cdf4f8dd33
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54494816"
---
# <a name="creating-a-custom-header-that-is-signed-and-or-encrypted"></a><span data-ttu-id="e0518-102">创建自定义标头进行签名和-或加密</span><span class="sxs-lookup"><span data-stu-id="e0518-102">Creating a custom header that is signed and-or encrypted</span></span>
<span data-ttu-id="e0518-103">在使用 WCF 客户端调用非 WCF 服务时，有时需要使用自定义 SOAP 标头。</span><span class="sxs-lookup"><span data-stu-id="e0518-103">When calling a non-WCF service using a WCF client it is sometimes necessary to use custom SOAP headers.</span></span> <span data-ttu-id="e0518-104">WCF 中有一个规范化 bug，该 bug 将阻止已签名和已加密的自定义标头使用非 WCF 服务。</span><span class="sxs-lookup"><span data-stu-id="e0518-104">There is a canonicalization bug in WCF that prevents custom headers that are signed and encrypted from working with a non-WCF service.</span></span> <span data-ttu-id="e0518-105">此问题是因默认 XML 命名空间的规范化错误导致的。</span><span class="sxs-lookup"><span data-stu-id="e0518-105">The problem is caused by the incorrect canonicalization of default XML namespaces.</span></span> <span data-ttu-id="e0518-106">此问题仅在使用已签名和/或已加密的自定义标头调用非 WCF 服务时发生。</span><span class="sxs-lookup"><span data-stu-id="e0518-106">This is only problematic when calling non-WCF services with custom headers that are signed and/or encrypted.</span></span>  <span data-ttu-id="e0518-107">当服务收到包含已签名和/或已加密的自定义标头的消息时，无法验证该签名。</span><span class="sxs-lookup"><span data-stu-id="e0518-107">When the service receives the message containing the signed and/or encrypted custom header it is unable to verify the signature.</span></span> <span data-ttu-id="e0518-108">此解决方法可避免出现规范化 bug，它允许与非 WCF 服务进行互操作，但不阻止与 WCF 服务进行互操作。</span><span class="sxs-lookup"><span data-stu-id="e0518-108">This workaround avoids the canonicalization bug, allows interoperability with non-WCF services, but does not prevent interoperability with WCF services.</span></span>  
  
## <a name="defining-the-custom-header"></a><span data-ttu-id="e0518-109">定义自定义标头</span><span class="sxs-lookup"><span data-stu-id="e0518-109">Defining the custom header</span></span>  
 <span data-ttu-id="e0518-110">自定义标头通过以下方式定义：定义消息协定并标记希望作为具有 <xref:System.ServiceModel.MessageHeaderAttribute> 属性的标头发送的成员。</span><span class="sxs-lookup"><span data-stu-id="e0518-110">Custom headers are defined by defining a message contract and marking the members you want to be sent as headers with a <xref:System.ServiceModel.MessageHeaderAttribute> attribute.</span></span> <span data-ttu-id="e0518-111">若要修复规范化 bug，您必须确保 XML 序列化程序声明的是带前缀的自定义标头的命名空间而不是默认命名空间声明。</span><span class="sxs-lookup"><span data-stu-id="e0518-111">To work around the canonicalization bug you must ensure that the XML serializer declares the namespace for the custom header with a prefix instead of a default namespace declaration.</span></span> <span data-ttu-id="e0518-112">下面的代码演示如何定义将用作带正确的命名空间声明的消息标头的数据类型。</span><span class="sxs-lookup"><span data-stu-id="e0518-112">The following code shows how to define the data type that will be used as a message header with the correct namespace declaration.</span></span>  
  
```  
[System.CodeDom.Compiler.GeneratedCodeAttribute("svcutil", "3.0.4506.648")]  
[System.SerializableAttribute()]  
[System.Diagnostics.DebuggerStepThroughAttribute()]  
[System.ComponentModel.DesignerCategoryAttribute("code")]  
[System.Xml.Serialization.XmlTypeAttribute(AnonymousType=true, Namespace="http://www.example.org/getMessage/")]  
public partial class msgHeaderElement  
{  
   // Define the XML namespace and force it to use an ‘h’ prefix  
    [System.Xml.Serialization.XmlNamespaceDeclarations]  
    public System.Xml.Serialization.XmlSerializerNamespaces _xsns = new System.Xml.Serialization.XmlSerializerNamespaces(new System.Xml.XmlQualifiedName[] { new System.Xml.XmlQualifiedName("h", "http://www.example.org/getMessage/") });  
  
    private string msgHeaderInputField;  
  [System.Xml.Serialization.XmlElementAttribute(Form=System.Xml.Schema.XmlSchemaForm.Unqualified, Order=0)]  
    public string msgHeaderInput  
    {  
        get  
        {  
            return this.msgHeaderInputField;  
        }  
        set  
        {  
            this.msgHeaderInputField = value;  
        }  
    }  
}  
```  
  
 <span data-ttu-id="e0518-113">此代码声明一个将用 XML 序列化程序进行序列化的名为 `msgHeaderElement` 的新类型。</span><span class="sxs-lookup"><span data-stu-id="e0518-113">This code declares a new type called `msgHeaderElement` that will be serialized with the XML Serializer.</span></span> <span data-ttu-id="e0518-114">当序列化此类型的实例时，它将定义一个带前缀“h”的命名空间，从而修复规范化 bug。</span><span class="sxs-lookup"><span data-stu-id="e0518-114">When an instance of this type is serialized, it will define a namespace with an ‘h’ prefix, thus working around the canonicalization bug.</span></span>  <span data-ttu-id="e0518-115">然后，消息协定将定义 `msgHeaderElement` 的实例并用 <xref:System.ServiceModel.MessageHeaderAttribute> 属性标记它，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="e0518-115">The message contract would then define an instance of `msgHeaderElement` and mark it with the <xref:System.ServiceModel.MessageHeaderAttribute> attribute as shown in the following example.</span></span>  
  
```  
[MessageContract]  
public  class MyMessageContract  
{  
   // other message contents...  
   [MessageHeader(ProductionLevel=ProtectionLevel.EncryptAndSign)]  
   public msgHeaderElement;  
   // other message contents...  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e0518-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0518-116">See also</span></span>
- [<span data-ttu-id="e0518-117">默认消息协定</span><span class="sxs-lookup"><span data-stu-id="e0518-117">Default Message Contract</span></span>](../../../../docs/framework/wcf/samples/default-message-contract.md)
- [<span data-ttu-id="e0518-118">消息协定</span><span class="sxs-lookup"><span data-stu-id="e0518-118">Message Contracts</span></span>](../../../../docs/framework/wcf/samples/message-contracts.md)
- [<span data-ttu-id="e0518-119">使用消息协定</span><span class="sxs-lookup"><span data-stu-id="e0518-119">Using Message Contracts</span></span>](../../../../docs/framework/wcf/feature-details/using-message-contracts.md)
