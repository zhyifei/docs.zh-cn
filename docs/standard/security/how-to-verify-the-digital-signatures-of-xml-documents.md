---
title: 如何：验证 XML 文档的数字签名
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- System.Security.Cryptography.SignedXml class
- signatures, cryptographic
- System.Security.Cryptography.RSACryptoServiceProvider class
- verifying signatures
- checking signatures
- XML digital signatures
- digital signatures, verifying
ms.assetid: a4d5ceb1-b9f5-47e8-9e4a-a2b39110002f
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 19537fa3e3e27c3446d22f1f1a8cf2faf472158e
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2019
ms.locfileid: "59307764"
---
# <a name="how-to-verify-the-digital-signatures-of-xml-documents"></a><span data-ttu-id="de05c-102">如何：验证 XML 文档的数字签名</span><span class="sxs-lookup"><span data-stu-id="de05c-102">How to: Verify the Digital Signatures of XML Documents</span></span>
<span data-ttu-id="de05c-103">可以使用 <xref:System.Security.Cryptography.Xml> 命名空间中的类来验证签有数字签名的 XML 数据。</span><span class="sxs-lookup"><span data-stu-id="de05c-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to verify XML data signed with a digital signature.</span></span> <span data-ttu-id="de05c-104">使用 XML 数字签名 (XMLDSIG)，你可以验证签名后的数据没有被更改。</span><span class="sxs-lookup"><span data-stu-id="de05c-104">XML digital signatures (XMLDSIG) allow you to verify that data was not altered after it was signed.</span></span> <span data-ttu-id="de05c-105">有关 XMLDSIG 标准的详细信息，请参阅万维网联合会 (W3C) 规范 <https://www.w3.org/TR/xmldsig-core/>。</span><span class="sxs-lookup"><span data-stu-id="de05c-105">For more information about the XMLDSIG standard, see the World Wide Web Consortium (W3C) specification at <https://www.w3.org/TR/xmldsig-core/>.</span></span>
  
 <span data-ttu-id="de05c-106">此过程中的代码示例演示如何验证 XML 数字签名中包含 <`Signature`> 元素。</span><span class="sxs-lookup"><span data-stu-id="de05c-106">The code example in this procedure demonstrates how to verify an XML digital signature contained in a <`Signature`> element.</span></span>  <span data-ttu-id="de05c-107">该示例检索密钥容器中 RSA 公钥，然后使用该密钥来验证签名。</span><span class="sxs-lookup"><span data-stu-id="de05c-107">The example retrieves an RSA public key from a key container and then uses the key to verify the signature.</span></span>  
  
 <span data-ttu-id="de05c-108">了解如何创建可以使用此方法验证数字签名，请参阅[如何：使用数字签名为 XML 文档](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="de05c-108">For information about how create a digital signature that can be verified using this technique, see [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
### <a name="to-verify-the-digital-signature-of-an-xml-document"></a><span data-ttu-id="de05c-109">验证 XML 文档的数字签名</span><span class="sxs-lookup"><span data-stu-id="de05c-109">To verify the digital signature of an XML document</span></span>  
  
1. <span data-ttu-id="de05c-110">若要验证文档，必须使用用于签名的同一非对称密钥。</span><span class="sxs-lookup"><span data-stu-id="de05c-110">To verify the document, you must use the same asymmetric key that was used for signing.</span></span>  <span data-ttu-id="de05c-111">创建 <xref:System.Security.Cryptography.CspParameters> 对象，并指定用于签名的密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="de05c-111">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container that was used for signing.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#2)]
     [!code-vb[HowToVerifyXMLDocumentRSA#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#2)]  
  
2. <span data-ttu-id="de05c-112">检索使用 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 类的公钥。</span><span class="sxs-lookup"><span data-stu-id="de05c-112">Retrieve the public key using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  <span data-ttu-id="de05c-113">当将 <xref:System.Security.Cryptography.CspParameters> 对象传递到 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 类的构造函数中时，会按名称从密钥容器自动加载密钥。</span><span class="sxs-lookup"><span data-stu-id="de05c-113">The key is automatically loaded from the key container by name when you pass the <xref:System.Security.Cryptography.CspParameters> object to the constructor of the <xref:System.Security.Cryptography.RSACryptoServiceProvider> class.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#3)]
     [!code-vb[HowToVerifyXMLDocumentRSA#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#3)]  
  
3. <span data-ttu-id="de05c-114">通过从磁盘加载 XML 文件来创建 <xref:System.Xml.XmlDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="de05c-114">Create an <xref:System.Xml.XmlDocument> object by loading an XML file from disk.</span></span>  <span data-ttu-id="de05c-115"><xref:System.Xml.XmlDocument> 对象包含要验证的已签名 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="de05c-115">The <xref:System.Xml.XmlDocument> object contains the signed XML document to verify.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#4)]
     [!code-vb[HowToVerifyXMLDocumentRSA#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#4)]  
  
4. <span data-ttu-id="de05c-116">创建一个新的 <xref:System.Security.Cryptography.Xml.SignedXml> 对象，并向其传递 <xref:System.Xml.XmlDocument> 对象。</span><span class="sxs-lookup"><span data-stu-id="de05c-116">Create a new <xref:System.Security.Cryptography.Xml.SignedXml> object and pass the <xref:System.Xml.XmlDocument> object to it.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#5)]
     [!code-vb[HowToVerifyXMLDocumentRSA#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#5)]  
  
5. <span data-ttu-id="de05c-117">找到 <`signature`> 元素并创建新的<xref:System.Xml.XmlNodeList>对象。</span><span class="sxs-lookup"><span data-stu-id="de05c-117">Find the <`signature`> element and create a new <xref:System.Xml.XmlNodeList> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#6)]
     [!code-vb[HowToVerifyXMLDocumentRSA#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#6)]  
  
6. <span data-ttu-id="de05c-118">加载的第一个 XML <`signature`> 元素插入<xref:System.Security.Cryptography.Xml.SignedXml>对象。</span><span class="sxs-lookup"><span data-stu-id="de05c-118">Load the XML of the first <`signature`> element into the <xref:System.Security.Cryptography.Xml.SignedXml> object.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#7)]
     [!code-vb[HowToVerifyXMLDocumentRSA#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#7)]  
  
7. <span data-ttu-id="de05c-119">使用 <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> 方法和 RSA 公钥检查签名。</span><span class="sxs-lookup"><span data-stu-id="de05c-119">Check the signature using the <xref:System.Security.Cryptography.Xml.SignedXml.CheckSignature%2A> method and the RSA public key.</span></span>  <span data-ttu-id="de05c-120">此方法返回一个指示成功或失败的布尔值。</span><span class="sxs-lookup"><span data-stu-id="de05c-120">This method returns a Boolean value that indicates success or failure.</span></span>  
  
     [!code-csharp[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#8)]
     [!code-vb[HowToVerifyXMLDocumentRSA#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="de05c-121">示例</span><span class="sxs-lookup"><span data-stu-id="de05c-121">Example</span></span>  
 <span data-ttu-id="de05c-122">此示例假定名为 `"test.xml"` 的文件与已编译程序存在于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="de05c-122">This example assumes that a file named `"test.xml"` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="de05c-123">`"test.xml"`必须使用中描述的方法签名文件[如何：使用数字签名为 XML 文档](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)。</span><span class="sxs-lookup"><span data-stu-id="de05c-123">The `"test.xml"` file must be signed using the techniques described in [How to: Sign XML Documents with Digital Signatures](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md).</span></span>  
  
 [!code-csharp[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/cs/sample.cs#1)]
 [!code-vb[HowToVerifyXMLDocumentRSA#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToVerifyXMLDocumentRSA/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="de05c-124">编译代码</span><span class="sxs-lookup"><span data-stu-id="de05c-124">Compiling the Code</span></span>  
  
-   <span data-ttu-id="de05c-125">若要编译此示例，需要包含对 `System.Security.dll` 的引用。</span><span class="sxs-lookup"><span data-stu-id="de05c-125">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="de05c-126">包括以下命名空间：<xref:System.Xml>、<xref:System.Security.Cryptography> 和 <xref:System.Security.Cryptography.Xml>。</span><span class="sxs-lookup"><span data-stu-id="de05c-126">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="de05c-127">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="de05c-127">.NET Framework Security</span></span>  
 <span data-ttu-id="de05c-128">切勿用纯文本存储或传输非对称密钥对的私钥。</span><span class="sxs-lookup"><span data-stu-id="de05c-128">Never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="de05c-129">有关对称和非对称加密密钥的详细信息，请参阅[生成的密钥进行加密和解密](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)。</span><span class="sxs-lookup"><span data-stu-id="de05c-129">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="de05c-130">切勿将私钥直接嵌入到源代码中。</span><span class="sxs-lookup"><span data-stu-id="de05c-130">Never embed a private key directly into your source code.</span></span>  <span data-ttu-id="de05c-131">从使用程序集可以轻松地读取嵌入的密钥[Ildasm.exe （IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)或通过在诸如记事本之类的文本编辑器中打开该程序集。</span><span class="sxs-lookup"><span data-stu-id="de05c-131">Embedded keys can be easily read from an assembly using the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de05c-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="de05c-132">See also</span></span>

- <xref:System.Security.Cryptography.Xml>
- [<span data-ttu-id="de05c-133">如何：使用数字签名为 XML 文档签名</span><span class="sxs-lookup"><span data-stu-id="de05c-133">How to: Sign XML Documents with Digital Signatures</span></span>](../../../docs/standard/security/how-to-sign-xml-documents-with-digital-signatures.md)
