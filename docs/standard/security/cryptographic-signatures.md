---
title: "加密签名"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c4e460c11e0e78d56a54da1dd178b3f8e9f381b6
ms.sourcegitcommit: 91691981897cf8451033cb01071d8f5d94017f97
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2018
---
# <a name="cryptographic-signatures"></a><span data-ttu-id="b9551-102">加密签名</span><span class="sxs-lookup"><span data-stu-id="b9551-102">Cryptographic Signatures</span></span>
<a name="top"></a> <span data-ttu-id="b9551-103">加密数字签名使用公钥算法提供数据完整性。</span><span class="sxs-lookup"><span data-stu-id="b9551-103">Cryptographic digital signatures use public key algorithms to provide data integrity.</span></span> <span data-ttu-id="b9551-104">如果使用数字签名对数据进行签名，则其他人可验证该签名，并且可证明这些数据确实是你发出的，并且在你签名之后未被更改。</span><span class="sxs-lookup"><span data-stu-id="b9551-104">When you sign data with a digital signature, someone else can verify the signature, and can prove that the data originated from you and was not altered after you signed it.</span></span> <span data-ttu-id="b9551-105">有关数字签名的详细信息，请参阅 [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md)。</span><span class="sxs-lookup"><span data-stu-id="b9551-105">For more information about digital signatures, see [Cryptographic Services](../../../docs/standard/security/cryptographic-services.md).</span></span>  
  
 <span data-ttu-id="b9551-106">本主题说明如何使用 <xref:System.Security.Cryptography?displayProperty=nameWithType> 命名空间中的类来生成和验证数字签名。</span><span class="sxs-lookup"><span data-stu-id="b9551-106">This topic explains how to generate and verify digital signatures using classes in the <xref:System.Security.Cryptography?displayProperty=nameWithType> namespace.</span></span>  
  
-   [<span data-ttu-id="b9551-107">生成签名</span><span class="sxs-lookup"><span data-stu-id="b9551-107">Generating Signatures</span></span>](#generate)  
  
-   [<span data-ttu-id="b9551-108">验证签名</span><span class="sxs-lookup"><span data-stu-id="b9551-108">Verifying Signatures</span></span>](#verify)  
  
<a name="generate"></a>   
## <a name="generating-signatures"></a><span data-ttu-id="b9551-109">生成签名</span><span class="sxs-lookup"><span data-stu-id="b9551-109">Generating Signatures</span></span>  
 <span data-ttu-id="b9551-110">数字签名通常应用于表示较大数据的哈希值。</span><span class="sxs-lookup"><span data-stu-id="b9551-110">Digital signatures are usually applied to hash values that represent larger data.</span></span> <span data-ttu-id="b9551-111">下面的示例将数字签名应用于哈希值。</span><span class="sxs-lookup"><span data-stu-id="b9551-111">The following example applies a digital signature to a hash value.</span></span> <span data-ttu-id="b9551-112">首先，创建 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 类的新实例以生成公钥/私钥对。</span><span class="sxs-lookup"><span data-stu-id="b9551-112">First, a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class is created to generate a public/private key pair.</span></span> <span data-ttu-id="b9551-113">然后，将 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 传递到 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> 类的新实例。</span><span class="sxs-lookup"><span data-stu-id="b9551-113">Next, the <xref:System.Security.Cryptography.RSACryptoServiceProvider> is passed to a new instance of the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class.</span></span> <span data-ttu-id="b9551-114">这将私钥传输给了实际执行数字签名的 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>。</span><span class="sxs-lookup"><span data-stu-id="b9551-114">This transfers the private key to the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter>, which actually performs the digital signing.</span></span> <span data-ttu-id="b9551-115">必须先指定要使用的哈希算法。然后才可以对哈希代码进行签名。</span><span class="sxs-lookup"><span data-stu-id="b9551-115">Before you can sign the hash code, you must specify a hash algorithm to use.</span></span> <span data-ttu-id="b9551-116">本示例使用 SHA1 算法。</span><span class="sxs-lookup"><span data-stu-id="b9551-116">This example uses the SHA1 algorithm.</span></span> <span data-ttu-id="b9551-117">最后，调用 <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> 方法以执行签名。</span><span class="sxs-lookup"><span data-stu-id="b9551-117">Finally, the <xref:System.Security.Cryptography.AsymmetricSignatureFormatter.CreateSignature%2A> method is called to perform the signing.</span></span>  
  
```vb  
Imports System  
Imports System.Security.Cryptography  
  
Module Module1  
    Sub Main()  
        'The hash value to sign.  
        Dim HashValue As Byte() = {59, 4, 248, 102, 77, 97, 142, 201, 210, 12, 224, 93, 25, 41, 100, 197, 213, 134, 130, 135}  
  
        'The value to hold the signed value.  
        Dim SignedHashValue() As Byte  
  
        'Generate a public/private key pair.  
        Dim RSA As New RSACryptoServiceProvider()  
  
        'Create an RSAPKCS1SignatureFormatter object and pass it   
        'the RSACryptoServiceProvider to transfer the private key.  
        Dim RSAFormatter As New RSAPKCS1SignatureFormatter(RSA)  
  
        'Set the hash algorithm to SHA1.  
        RSAFormatter.SetHashAlgorithm("SHA1")  
  
        'Create a signature for HashValue and assign it to   
        'SignedHashValue.  
        SignedHashValue = RSAFormatter.CreateSignature(HashValue)  
    End Sub  
End Module  
  
using System;  
using System.Security.Cryptography;  
```  
  
```csharp  
class Class1  
{  
   static void Main()  
   {  
      //The hash value to sign.  
      byte[] HashValue = {59,4,248,102,77,97,142,201,210,12,224,93,25,41,100,197,213,134,130,135};  
  
      //The value to hold the signed value.  
      byte[] SignedHashValue;  
  
      //Generate a public/private key pair.  
      RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
  
      //Create an RSAPKCS1SignatureFormatter object and pass it the   
      //RSACryptoServiceProvider to transfer the private key.  
      RSAPKCS1SignatureFormatter RSAFormatter = new RSAPKCS1SignatureFormatter(RSA);  
  
      //Set the hash algorithm to SHA1.  
      RSAFormatter.SetHashAlgorithm("SHA1");  
  
      //Create a signature for HashValue and assign it to   
      //SignedHashValue.  
      SignedHashValue = RSAFormatter.CreateSignature(HashValue);  
   }  
}  
```  
  
### <a name="signing-xml-files"></a><span data-ttu-id="b9551-118">对 XML 文件进行签名</span><span class="sxs-lookup"><span data-stu-id="b9551-118">Signing XML Files</span></span>  
 <span data-ttu-id="b9551-119">.NET Framework 提供可实现 XML 签名的 <xref:System.Security.Cryptography.Xml> 命名空间。</span><span class="sxs-lookup"><span data-stu-id="b9551-119">The .NET Framework provides the <xref:System.Security.Cryptography.Xml> namespace, which enables you sign XML.</span></span> <span data-ttu-id="b9551-120">当想要验证 XML 是否源自某个源时，对 XML 进行签名就变得非常重要。</span><span class="sxs-lookup"><span data-stu-id="b9551-120">Signing XML is important when you want to verify that the XML originates from a certain source.</span></span> <span data-ttu-id="b9551-121">例如，如果你正在利用使用 XML 的股票报价服务，则如果已对 XML 签名，你就可以验证该 XML 的源。</span><span class="sxs-lookup"><span data-stu-id="b9551-121">For example, if you are using a stock quote service that uses XML, you can verify the source of the XML if it is signed.</span></span>  
  
 <span data-ttu-id="b9551-122">此命名空间中的类遵循[XML 签名语法和处理建议](http://www.w3.org/TR/xmldsig-core/)从 World Wide Web Consortium。</span><span class="sxs-lookup"><span data-stu-id="b9551-122">The classes in this namespace follow the [XML-Signature Syntax and Processing recommendation](http://www.w3.org/TR/xmldsig-core/) from the World Wide Web Consortium.</span></span>  
  
 [<span data-ttu-id="b9551-123">返回页首</span><span class="sxs-lookup"><span data-stu-id="b9551-123">Back to top</span></span>](#top)  
  
<a name="verify"></a>   
## <a name="verifying-signatures"></a><span data-ttu-id="b9551-124">验证签名</span><span class="sxs-lookup"><span data-stu-id="b9551-124">Verifying Signatures</span></span>  
 <span data-ttu-id="b9551-125">若要验证数据是否是由特定方进行签名的，则必须具有以下信息：</span><span class="sxs-lookup"><span data-stu-id="b9551-125">To verify that data was signed by a particular party, you must have the following information:</span></span>  
  
-   <span data-ttu-id="b9551-126">对数据进行签名的一方的公钥。</span><span class="sxs-lookup"><span data-stu-id="b9551-126">The public key of the party that signed the data.</span></span>  
  
-   <span data-ttu-id="b9551-127">数字签名。</span><span class="sxs-lookup"><span data-stu-id="b9551-127">The digital signature.</span></span>  
  
-   <span data-ttu-id="b9551-128">已签名的数据。</span><span class="sxs-lookup"><span data-stu-id="b9551-128">The data that was signed.</span></span>  
  
-   <span data-ttu-id="b9551-129">签名方使用的哈希算法。</span><span class="sxs-lookup"><span data-stu-id="b9551-129">The hash algorithm used by the signer.</span></span>  
  
 <span data-ttu-id="b9551-130">若要验证由 <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> 类签署的签名，请使用 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 类。</span><span class="sxs-lookup"><span data-stu-id="b9551-130">To verify a signature signed by the <xref:System.Security.Cryptography.RSAPKCS1SignatureFormatter> class, use the <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class.</span></span> <span data-ttu-id="b9551-131">必须向 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 类提供签名者的公钥。</span><span class="sxs-lookup"><span data-stu-id="b9551-131">The <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> class must be supplied the public key of the signer.</span></span> <span data-ttu-id="b9551-132">将需要模数和指数的值以指定公钥。</span><span class="sxs-lookup"><span data-stu-id="b9551-132">You will need the values of the modulus and the exponent to specify the public key.</span></span> <span data-ttu-id="b9551-133">（生成公钥/私钥对的一方应提供这些值）。首先创建<xref:System.Security.Cryptography.RSACryptoServiceProvider>对象以保存将验证签名，并进行初始化的公共密钥<xref:System.Security.Cryptography.RSAParameters>结构指定的公钥的模数值和指数值。</span><span class="sxs-lookup"><span data-stu-id="b9551-133">(The party that generated the public/private key pair should provide these values.) First create an <xref:System.Security.Cryptography.RSACryptoServiceProvider> object to hold the public key that will verify the signature, and then initialize an <xref:System.Security.Cryptography.RSAParameters> structure to the modulus and exponent values that specify the public key.</span></span>  
  
 <span data-ttu-id="b9551-134">下面的代码显示 <xref:System.Security.Cryptography.RSAParameters> 结构的创建。</span><span class="sxs-lookup"><span data-stu-id="b9551-134">The following code shows the creation of an <xref:System.Security.Cryptography.RSAParameters> structure.</span></span> <span data-ttu-id="b9551-135">`Modulus` 属性设置为名为 `ModulusData` 的字节数组的值， `Exponent` 属性设置为名为 `ExponentData`的字节数组的值。</span><span class="sxs-lookup"><span data-stu-id="b9551-135">The `Modulus` property is set to the value of a byte array called `ModulusData` and the `Exponent` property is set to the value of a byte array called `ExponentData`.</span></span>  
  
```vb  
Dim RSAKeyInfo As RSAParameters  
RSAKeyInfo.Modulus = ModulusData  
RSAKeyInfo.Exponent = ExponentData  
```  
  
```csharp  
RSAParameters RSAKeyInfo;  
RSAKeyInfo.Modulus = ModulusData;  
RSAKeyInfo.Exponent = ExponentData;  
```  
  
 <span data-ttu-id="b9551-136">创建 <xref:System.Security.Cryptography.RSAParameters> 对象后，可将 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 类的新实例初始化为 <xref:System.Security.Cryptography.RSAParameters>中指定的值。</span><span class="sxs-lookup"><span data-stu-id="b9551-136">After you have created the <xref:System.Security.Cryptography.RSAParameters> object, you can initialize a new instance of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class to the values specified in <xref:System.Security.Cryptography.RSAParameters>.</span></span> <span data-ttu-id="b9551-137">然后将 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 传递到 <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> 的构造函数以传输密钥。</span><span class="sxs-lookup"><span data-stu-id="b9551-137">The <xref:System.Security.Cryptography.RSACryptoServiceProvider> is, in turn, passed to the constructor of an <xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter> to transfer the key.</span></span>  
  
 <span data-ttu-id="b9551-138">下面的示例阐释此过程。</span><span class="sxs-lookup"><span data-stu-id="b9551-138">The following example illustrates this process.</span></span> <span data-ttu-id="b9551-139">在本示例中， `HashValue` 和 `SignedHashValue` 是由远程方提供的字节数组。</span><span class="sxs-lookup"><span data-stu-id="b9551-139">In this example, `HashValue` and `SignedHashValue` are arrays of bytes provided by a remote party.</span></span> <span data-ttu-id="b9551-140">远程方已使用 SHA1 算法对 `HashValue` 进行了签名，从而生成了数字签名 `SignedHashValue`。</span><span class="sxs-lookup"><span data-stu-id="b9551-140">The remote party has signed the `HashValue` using the SHA1 algorithm, producing the digital signature `SignedHashValue`.</span></span> <span data-ttu-id="b9551-141">必须向</span><span class="sxs-lookup"><span data-stu-id="b9551-141">The</span></span>  
  
 <span data-ttu-id="b9551-142"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> 方法验证数字签名是否有效，并且是否已用于对 `HashValue` 进行签名。</span><span class="sxs-lookup"><span data-stu-id="b9551-142"><xref:System.Security.Cryptography.RSAPKCS1SignatureDeformatter.VerifySignature%2A?displayProperty=nameWithType> method verifies that the digital signature is valid and was used to sign the `HashValue`.</span></span>  
  
```vb  
Dim RSA As New RSACryptoServiceProvider()  
RSA.ImportParameters(RSAKeyInfo)  
Dim RSADeformatter As New RSAPKCS1SignatureDeformatter(RSA)  
RSADeformatter.SetHashAlgorithm("SHA1")  
If RSADeformatter.VerifySignature(HashValue, SignedHashValue) Then  
   Console.WriteLine("The signature is valid.")  
Else  
   Console.WriteLine("The signture is not valid.")  
End If  
```  
  
```csharp  
RSACryptoServiceProvider RSA = new RSACryptoServiceProvider();  
RSA.ImportParameters(RSAKeyInfo);  
RSAPKCS1SignatureDeformatter RSADeformatter = new RSAPKCS1SignatureDeformatter(RSA);  
RSADeformatter.SetHashAlgorithm("SHA1");  
if(RSADeformatter.VerifySignature(HashValue, SignedHashValue))  
{  
   Console.WriteLine("The signature is valid.");  
}  
else  
{  
   Console.WriteLine("The signature is not valid.");  
}  
```  
  
 <span data-ttu-id="b9551-143">如果签名有效，则此代码段将显示“`The signature is valid`”，如果无效，则显示“`The signature is not valid`”。</span><span class="sxs-lookup"><span data-stu-id="b9551-143">This code fragment will display "`The signature is valid`" if the signature is valid and "`The signature is not valid`" if it is not.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9551-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="b9551-144">See Also</span></span>  
 [<span data-ttu-id="b9551-145">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="b9551-145">Cryptographic Services</span></span>](../../../docs/standard/security/cryptographic-services.md)
