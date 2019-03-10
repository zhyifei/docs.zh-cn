---
title: 加密签名
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- digital signatures
- cryptography [.NET Framework], signatures
- digital signatures, XML signing
- signatures, cryptographic
- digital signatures, generating
- verifying signatures
- generating signatures
- digital signatures, about
- encryption [.NET Framework], signatures
- security [.NET Framework], signatures
- XML signing
- digital signatures, verifying
- signing XML
ms.assetid: aa87cb7f-e608-4a81-948b-c9b8a1225783
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 15fd79a1289bd54b81db551abbdfcd63deef3e24
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57710298"
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="23fd0-102">加密签名</span><span class="sxs-lookup"><span data-stu-id="23fd0-102">Cryptographic Signatures</span></span>

<a name="top"></a> <span data-ttu-id="23fd0-103">加密数字签名使用公钥算法提供数据完整性。</span><span class="sxs-lookup"><span data-stu-id="23fd0-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="23fd0-104">如果使用数字签名对数据进行签名，则其他人可验证该签名，并且可证明这些数据确实是你发出的，并且在你签名之后未被更改。</span><span class="sxs-lookup"><span data-stu-id="23fd0-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="23fd0-105">有关数字签名的详细信息，请参阅 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)。</span><span class="sxs-lookup"><span data-stu-id="23fd0-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>

<span data-ttu-id="23fd0-106">本主题说明如何使用 <xref:System.Security.Cryptography?displayProperty=nameWithType> 命名空间中的类来生成和验证数字签名。</span><span class="sxs-lookup"><span data-stu-id="23fd0-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>

- [<span data-ttu-id="23fd0-107">生成签名</span><span class="sxs-lookup"><span data-stu-id="23fd0-107">Generating Signatures</span></span>](#generate)

- [<span data-ttu-id="23fd0-108">验证签名</span><span class="sxs-lookup"><span data-stu-id="23fd0-108">Verifying Signatures</span></span>](#verify)

<a name="generate"></a>

## <a name="generating-signatures"></a><span data-ttu-id="23fd0-109">生成签名</span><span class="sxs-lookup"><span data-stu-id="23fd0-109">Generating Signatures</span></span>

<span data-ttu-id="23fd0-110">数字签名通常应用于表示较大数据的哈希值。</span><span class="sxs-lookup"><span data-stu-id="23fd0-110">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="23fd0-111">下面的示例将数字签名应用于哈希值。</span><span class="sxs-lookup"><span data-stu-id="23fd0-111">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="23fd0-112">首先，创建 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 类的新实例以生成公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="23fd0-112">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="23fd0-113">然后，将 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 传递到 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="23fd0-113">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="23fd0-114">这将私钥传输给了实际执行数字签名的 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>。</span><span class="sxs-lookup"><span data-stu-id="23fd0-114">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="23fd0-115">必须先指定要使用的哈希算法。然后才可以对哈希代码进行签名。</span><span class="sxs-lookup"><span data-stu-id="23fd0-115">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="23fd0-116">本示例使用 SHA1 算法。</span><span class="sxs-lookup"><span data-stu-id="23fd0-116">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="23fd0-117">最后，调用 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> 方法以执行签名。</span><span class="sxs-lookup"><span data-stu-id="23fd0-117">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>

```vb
Imports System
Imports System.Security.Cryptography

Module Module1
    Sub Main()
        'The hash value to sign.
        Dim hashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}

        'The value to hold the signed value.
        Dim signedHashValue() As Byte

        'Generate a public/private key pair.
        Dim rsa As New RSACryptoServiceProvider()

        'Create an RSAPKCS1SignatureFormatter object and pass it
        'the RSACryptoServiceProvider to transfer the private key.
        Dim rsaFormatter As New RSAPKCS1SignatureFormatter(rsa)

        'Set the hash algorithm to SHA1.
        rsaFormatter.SetHashAlgorithm("SHA1")

        'Create a signature for hashValue and assign it to
        'signedHashValue.
        signedHashValue = rsaFormatter.CreateSignature(hashValue)
    End Sub
End Module
```

```csharp
using System;
using System.Security.Cryptography;

class Class1
{
   static void Main()
   {
      //The hash value to sign.
      byte[] hashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};

      //The value to hold the signed value.
      byte[] signedHashValue;

      //Generate a public/private key pair.
      RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();

      //Create an RSAPKCS1SignatureFormatter object and pass it the
      //RSACryptoServiceProvider to transfer the private key.
      RSAPKCS1SignatureFormatter rsaFormatter = new RSAPKCS1SignatureFormatter(rsa);

      //Set the hash algorithm to SHA1.
      rsaFormatter.SetHashAlgorithm("SHA1");

      //Create a signature for hashValue and assign it to
      //signedHashValue.
      signedHashValue = rsaFormatter.CreateSignature(hashValue);
   }
}
```

### <a name="signing-xml-files"></a><span data-ttu-id="23fd0-118">对 XML 文件进行签名</span><span class="sxs-lookup"><span data-stu-id="23fd0-118">Signing XML Files</span></span>

<span data-ttu-id="23fd0-119">.NET Framework 提供可实现 XML 签名的 <xref:System.Security.Cryptography.Xml> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="23fd0-119">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="23fd0-120">当想要验证 XML 是否源自某个源时，对 XML 进行签名就变得非常重要。</span><span class="sxs-lookup"><span data-stu-id="23fd0-120">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="23fd0-121">例如，如果你正在利用使用 XML 的股票报价服务，则如果已对 XML 签名，你就可以验证该 XML 的源。</span><span class="sxs-lookup"><span data-stu-id="23fd0-121">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>

<span data-ttu-id="23fd0-122">此命名空间中的类遵循来自万维网联合会的 [XML 签名语法和处理建议](https://www.w3.org/TR/xmldsig-core/) 。</span><span class="sxs-lookup"><span data-stu-id="23fd0-122">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](https://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>

[<span data-ttu-id="23fd0-123">返回页首</span><span class="sxs-lookup"><span data-stu-id="23fd0-123">Back to top</span></span>](#top)

<a name="verify"></a>

## <a name="verifying-signatures"></a><span data-ttu-id="23fd0-124">验证签名</span><span class="sxs-lookup"><span data-stu-id="23fd0-124">Verifying Signatures</span></span>

<span data-ttu-id="23fd0-125">若要验证数据是否是由特定方进行签名的，则必须具有以下信息：</span><span class="sxs-lookup"><span data-stu-id="23fd0-125">To verify that data was signed by a particular party, you must have the following information:</span></span>

- <span data-ttu-id="23fd0-126">对数据进行签名的一方的公钥。</span><span class="sxs-lookup"><span data-stu-id="23fd0-126">The public key of the party that signed the data.</span></span>

- <span data-ttu-id="23fd0-127">数字签名。</span><span class="sxs-lookup"><span data-stu-id="23fd0-127">The digital signature.</span></span>

- <span data-ttu-id="23fd0-128">已签名的数据。</span><span class="sxs-lookup"><span data-stu-id="23fd0-128">The data that was signed.</span></span>

- <span data-ttu-id="23fd0-129">签名方使用的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="23fd0-129">The hash algorithm used by the signer.</span></span>

<span data-ttu-id="23fd0-130">若要验证由 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> 类签署的签名，请使用 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 类。</span><span class="sxs-lookup"><span data-stu-id="23fd0-130">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="23fd0-131">必须向 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 类提供签名者的公钥。</span><span class="sxs-lookup"><span data-stu-id="23fd0-131">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="23fd0-132">将需要模数和指数的值以指定公钥。</span><span class="sxs-lookup"><span data-stu-id="23fd0-132">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="23fd0-133">（生成公钥/私钥对的一方应提供这些值）。首先创建一个 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 对象以保存将验证签名的公钥，然后将 <xref:System.Security.Cryptography.RSAParameters> 结构初始化为指定该公钥的模数值和指数值。</span><span class="sxs-lookup"><span data-stu-id="23fd0-133">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>

<span data-ttu-id="23fd0-134">下面的代码显示 <xref:System.Security.Cryptography.RSAParameters> 结构的创建。</span><span class="sxs-lookup"><span data-stu-id="23fd0-134">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="23fd0-135">`Modulus` 属性设置为名为 `modulusData` 的字节数组的值， `Exponent` 属性设置为名为 `exponentData`的字节数组的值。</span><span class="sxs-lookup"><span data-stu-id="23fd0-135">The `Modulus` property is set to the value of a byte array called `modulusData` and the `Exponent` property is set to the value of a byte array called `exponentData`.</span></span>

```vb
Dim rsaKeyInfo As RSAParameters
rsaKeyInfo.Modulus = modulusData
rsaKeyInfo.Exponent = exponentData
```

```csharp
RSAParameters rsaKeyInfo;
rsaKeyInfo.Modulus = modulusData;
rsaKeyInfo.Exponent = exponentData;
```

<span data-ttu-id="23fd0-136">创建 <xref:System.Security.Cryptography.RSAParameters> 对象后，可将 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 类的新实例初始化为 <xref:System.Security.Cryptography.RSAParameters>中指定的值。</span><span class="sxs-lookup"><span data-stu-id="23fd0-136">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="23fd0-137">然后将 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 传递到 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 的构造函数以传输密钥。</span><span class="sxs-lookup"><span data-stu-id="23fd0-137">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>

<span data-ttu-id="23fd0-138">下面的示例阐释此过程。</span><span class="sxs-lookup"><span data-stu-id="23fd0-138">The following example illustrates this process.</span></span> <span data-ttu-id="23fd0-139">在本示例中， `hashValue` 和 `signedHashValue` 是由远程方提供的字节数组。</span><span class="sxs-lookup"><span data-stu-id="23fd0-139">In this example, `hashValue` and `signedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="23fd0-140">远程方已使用 SHA1 算法对 `hashValue` 进行了签名，从而生成了数字签名 `signedHashValue`。</span><span class="sxs-lookup"><span data-stu-id="23fd0-140">The remote party has signed the `hashValue` using the SHA1 algorithm, producing the digital signature `signedHashValue`.</span></span> <span data-ttu-id="23fd0-141"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType>方法验证数字签名是否有效，并且用于签署`hashValue`。</span><span class="sxs-lookup"><span data-stu-id="23fd0-141">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `hashValue`.</span></span>

```vb
Dim rsa As New RSACryptoServiceProvider()
rsa.ImportParameters(rsaKeyInfo)
Dim rsaDeformatter As New RSAPKCS1SignatureDeformatter(rsa)
rsaDeformatter.SetHashAlgorithm("SHA1")
If rsaDeformatter.VerifySignature(hashValue, signedHashValue) Then
   Console.WriteLine("The signature is valid.")
Else
   Console.WriteLine("The signature is not valid.")
End If
```

```csharp
RSACryptoServiceProvider rsa = new RSACryptoServiceProvider();
rsa.ImportParameters(rsaKeyInfo);
RSAPKCS1SignatureDeformatter rsaDeformatter = new RSAPKCS1SignatureDeformatter(rsa);
rsaDeformatter.SetHashAlgorithm("SHA1");
if(rsaDeformatter.VerifySignature(hashValue, signedHashValue))
{
   Console.WriteLine("The signature is valid.");
}
else
{
   Console.WriteLine("The signature is not valid.");
}
```

<span data-ttu-id="23fd0-142">如果签名有效，则此代码段将显示“`The signature is valid`”，如果无效，则显示“`The signature is not valid`”。</span><span class="sxs-lookup"><span data-stu-id="23fd0-142">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>

## <a name="see-also"></a><span data-ttu-id="23fd0-143">请参阅</span><span class="sxs-lookup"><span data-stu-id="23fd0-143">See also</span></span>

- [<span data-ttu-id="23fd0-144">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="23fd0-144">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
