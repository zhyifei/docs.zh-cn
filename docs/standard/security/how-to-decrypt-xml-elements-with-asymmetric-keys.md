---
title: "如何：用非对称密钥对 XML 元素进行解密"
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
- System.Security.Cryptography.RSACryptoServiceProvider class
- asymmetric keys
- System.Security.Cryptography.EncryptedXml class
- XML encryption
- decryption
ms.assetid: dd5de491-dafe-4b94-966d-99714b2e754a
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 698a542765cf8599a2f07e747669893502b75045
ms.sourcegitcommit: ba765893e3efcece67d99fd6d5ce0074b050d1d9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/02/2018
---
# <a name="how-to-decrypt-xml-elements-with-asymmetric-keys"></a><span data-ttu-id="73b01-102">如何：用非对称密钥对 XML 元素进行解密</span><span class="sxs-lookup"><span data-stu-id="73b01-102">How to: Decrypt XML Elements with Asymmetric Keys</span></span>
<span data-ttu-id="73b01-103">可以使用 <xref:System.Security.Cryptography.Xml> 命名空间中的类对 XML 文档内的元素进行加密和解密。</span><span class="sxs-lookup"><span data-stu-id="73b01-103">You can use the classes in the <xref:System.Security.Cryptography.Xml> namespace to encrypt and decrypt an element within an XML document.</span></span>  <span data-ttu-id="73b01-104">XML 加密是交换或存储加密的 XML 数据的一种标准方式，使用后就无需担心数据被轻易读取。</span><span class="sxs-lookup"><span data-stu-id="73b01-104">XML Encryption is a standard way to exchange or store encrypted XML data, without worrying about the data being easily read.</span></span>  <span data-ttu-id="73b01-105">有关 XML 加密标准的详细信息，请参阅万维网联合会 (W3C) 建议[XML 签名语法和处理](https://www.w3.org/TR/xmldsig-core/)。</span><span class="sxs-lookup"><span data-stu-id="73b01-105">For more information about the XML Encryption standard, see the World Wide Web Consortium (W3C) recommendation [XML Signature Syntax and Processing](https://www.w3.org/TR/xmldsig-core/).</span></span>  
  
 <span data-ttu-id="73b01-106">此过程中的示例使用中所述的方法进行加密的 XML 元素进行解密[如何： 用非对称密钥加密 XML 元素](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="73b01-106">The example in this procedure decrypts an XML element that was encrypted using the methods described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  <span data-ttu-id="73b01-107">它找到一个 <`EncryptedData`> 元素，解密该元素，然后将其替换为原始纯文本 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="73b01-107">It finds an <`EncryptedData`> element, decrypts the element, and then replaces the element with the original plaintext XML element.</span></span>  
  
 <span data-ttu-id="73b01-108">此示例使用两个密钥对 XML 元素进行解密。</span><span class="sxs-lookup"><span data-stu-id="73b01-108">This example decrypts an XML element using two keys.</span></span>  <span data-ttu-id="73b01-109">它从密钥容器中检索以前生成的 RSA 私钥，然后使用 RSA 密钥解密存储在 <`EncryptedData`> 元素的 <`EncryptedKey`> 元素中的会话密钥。</span><span class="sxs-lookup"><span data-stu-id="73b01-109">It retrieves a previously generated RSA private key from a key container, and then uses the RSA key to decrypt a session key stored in the <`EncryptedKey`> element of the <`EncryptedData`> element.</span></span>  <span data-ttu-id="73b01-110">然后此示例使用会话密钥对 XML 元素进行解密。</span><span class="sxs-lookup"><span data-stu-id="73b01-110">The example then uses the session key to decrypt the XML element.</span></span>  
  
 <span data-ttu-id="73b01-111">此示例适用于以下情况：多个应用程序必须共享加密数据，或应用程序必须保存其每次运行之间的加密数据。</span><span class="sxs-lookup"><span data-stu-id="73b01-111">This example is appropriate for situations where multiple applications have to share encrypted data or where an application has to save encrypted data between the times that it runs.</span></span>  
  
### <a name="to-decrypt-an-xml-element-with-an-asymmetric-key"></a><span data-ttu-id="73b01-112">用非对称密钥对 XML 元素进行解密</span><span class="sxs-lookup"><span data-stu-id="73b01-112">To decrypt an XML element with an asymmetric key</span></span>  
  
1.  <span data-ttu-id="73b01-113">创建 <xref:System.Security.Cryptography.CspParameters> 对象，并指定密钥容器的名称。</span><span class="sxs-lookup"><span data-stu-id="73b01-113">Create a <xref:System.Security.Cryptography.CspParameters> object and specify the name of the key container.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#2)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#2)]  
  
2.  <span data-ttu-id="73b01-114">使用 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 对象从容器中检索以前生成的非对称密钥。</span><span class="sxs-lookup"><span data-stu-id="73b01-114">Retrieve a previously generated asymmetric key from the container using the <xref:System.Security.Cryptography.RSACryptoServiceProvider> object.</span></span>  <span data-ttu-id="73b01-115">当将 <xref:System.Security.Cryptography.CspParameters> 对象传递到 <xref:System.Security.Cryptography.RSACryptoServiceProvider> 构造函数中时，将自动从密钥容器中检索到密钥。</span><span class="sxs-lookup"><span data-stu-id="73b01-115">The key is automatically retrieved from the key container when you pass the <xref:System.Security.Cryptography.CspParameters> object to the <xref:System.Security.Cryptography.RSACryptoServiceProvider> constructor.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#3)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#3)]  
  
3.  <span data-ttu-id="73b01-116">创建新 <xref:System.Security.Cryptography.Xml.EncryptedXml> 对象以对文档进行解密。</span><span class="sxs-lookup"><span data-stu-id="73b01-116">Create a new <xref:System.Security.Cryptography.Xml.EncryptedXml> object to decrypt the document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#5)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#5)]  
  
4.  <span data-ttu-id="73b01-117">添加一个密钥/名称映射，以便 RSA 密钥与应该进行解密的文档中的元素相关联。</span><span class="sxs-lookup"><span data-stu-id="73b01-117">Add a key/name mapping to associate the RSA key with the element within the document that should be decrypted.</span></span>  <span data-ttu-id="73b01-118">必须使用与加密文档时所用密钥名称相同的名称。</span><span class="sxs-lookup"><span data-stu-id="73b01-118">You must use the same name for the key that you used when you encrypted the document.</span></span>  <span data-ttu-id="73b01-119">请注意，此名称独立于用来标识在步骤 1 中指定的密钥容器中的密钥名称。</span><span class="sxs-lookup"><span data-stu-id="73b01-119">Note that this name is separate from the name used to identify the key in the key container specified in step 1.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#6)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#6)]  
  
5.  <span data-ttu-id="73b01-120">调用 <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> 方法以解密 <`EncryptedData`> 元素。</span><span class="sxs-lookup"><span data-stu-id="73b01-120">Call the <xref:System.Security.Cryptography.Xml.EncryptedXml.DecryptDocument%2A> method to decrypt the <`EncryptedData`> element.</span></span>  <span data-ttu-id="73b01-121">此方法使用 RSA 密钥来解密会话密钥，并自动使用会话密钥来解密 XML 元素。</span><span class="sxs-lookup"><span data-stu-id="73b01-121">This method uses the RSA key to decrypt the session key and automatically uses the session key to decrypt the XML element.</span></span>  <span data-ttu-id="73b01-122">它还会自动将 <`EncryptedData`> 元素替换为原始的纯文本。</span><span class="sxs-lookup"><span data-stu-id="73b01-122">It also automatically replaces the <`EncryptedData`> element with the original plaintext.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#7)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#7)]  
  
6.  <span data-ttu-id="73b01-123">保存 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="73b01-123">Save the XML document.</span></span>  
  
     [!code-csharp[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#8)]
     [!code-vb[HowToDecryptXMLElementAsymmetric#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#8)]  
  
## <a name="example"></a><span data-ttu-id="73b01-124">示例</span><span class="sxs-lookup"><span data-stu-id="73b01-124">Example</span></span>  
 <span data-ttu-id="73b01-125">此示例假定名为 `test.xml` 的文件与已编译程序存在于同一目录中。</span><span class="sxs-lookup"><span data-stu-id="73b01-125">This example assumes that a file named `test.xml` exists in the same directory as the compiled program.</span></span>  <span data-ttu-id="73b01-126">它还假定`test.xml`包含使用中所述的技术加密的 XML 元素[如何： 用非对称密钥加密 XML 元素](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)。</span><span class="sxs-lookup"><span data-stu-id="73b01-126">It also assumes that `test.xml` contains an XML element that was encrypted using the techniques described in [How to: Encrypt XML Elements with Asymmetric Keys](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md).</span></span>  
  
 [!code-csharp[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/csharp/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/cs/sample.cs#1)]
 [!code-vb[HowToDecryptXMLElementAsymmetric#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/HowToDecryptXMLElementAsymmetric/vb/sample.vb#1)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="73b01-127">编译代码</span><span class="sxs-lookup"><span data-stu-id="73b01-127">Compiling the Code</span></span>  
  
-   <span data-ttu-id="73b01-128">若要编译此示例，需要包含对 `System.Security.dll` 的引用。</span><span class="sxs-lookup"><span data-stu-id="73b01-128">To compile this example, you need to include a reference to `System.Security.dll`.</span></span>  
  
-   <span data-ttu-id="73b01-129">包括以下命名空间：<xref:System.Xml>、<xref:System.Security.Cryptography> 和 <xref:System.Security.Cryptography.Xml>。</span><span class="sxs-lookup"><span data-stu-id="73b01-129">Include the following namespaces: <xref:System.Xml>, <xref:System.Security.Cryptography>, and <xref:System.Security.Cryptography.Xml>.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="73b01-130">.NET Framework 安全性</span><span class="sxs-lookup"><span data-stu-id="73b01-130">.NET Framework Security</span></span>  
 <span data-ttu-id="73b01-131">永远不要以纯文本形式存储对称加密密钥，也不要以纯文本形式在计算机之间传输对称密钥。</span><span class="sxs-lookup"><span data-stu-id="73b01-131">Never store a symmetric cryptographic key in plaintext or transfer a symmetric key between machines in plaintext.</span></span>  <span data-ttu-id="73b01-132">此外，绝不存储或传输纯文本形式的非对称密钥的私钥。</span><span class="sxs-lookup"><span data-stu-id="73b01-132">Additionally, never store or transfer the private key of an asymmetric key pair in plaintext.</span></span>  <span data-ttu-id="73b01-133">有关对称和非对称加密密钥的详细信息，请参阅[生成加密和解密的密钥](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md)。</span><span class="sxs-lookup"><span data-stu-id="73b01-133">For more information about symmetric and asymmetric cryptographic keys, see [Generating Keys for Encryption and Decryption](../../../docs/standard/security/generating-keys-for-encryption-and-decryption.md).</span></span>  
  
 <span data-ttu-id="73b01-134">绝不将密钥直接嵌入源代码。</span><span class="sxs-lookup"><span data-stu-id="73b01-134">Never embed a key directly into your source code.</span></span>  <span data-ttu-id="73b01-135">读取嵌入的密钥可以被轻松从程序集使用[Ildasm.exe （IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)或通过在诸如记事本之类的文本编辑器中打开程序集。</span><span class="sxs-lookup"><span data-stu-id="73b01-135">Embedded keys can be easily read from an assembly by using [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) or by opening the assembly in a text editor such as Notepad.</span></span>  
  
 <span data-ttu-id="73b01-136">当你使用加密密钥执行操作后，通过将每个字节设置为零或通过调用托管加密类的 <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> 方法来将它从内存中清除。</span><span class="sxs-lookup"><span data-stu-id="73b01-136">When you are done using a cryptographic key, clear it from memory by setting each byte to zero or by calling the <xref:System.Security.Cryptography.SymmetricAlgorithm.Clear%2A> method of the managed cryptography class.</span></span>  <span data-ttu-id="73b01-137">加密密钥有时可从内存由调试器读取，或从硬盘读取（如果内存位置分页到磁盘）。</span><span class="sxs-lookup"><span data-stu-id="73b01-137">Cryptographic keys can sometimes be read from memory by a debugger or read from a hard drive if the memory location is paged to disk.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="73b01-138">请参阅</span><span class="sxs-lookup"><span data-stu-id="73b01-138">See Also</span></span>  
 <xref:System.Security.Cryptography.Xml>  
 [<span data-ttu-id="73b01-139">如何：使用非对称密钥加密 XML 元素</span><span class="sxs-lookup"><span data-stu-id="73b01-139">How to: Encrypt XML Elements with Asymmetric Keys</span></span>](../../../docs/standard/security/how-to-encrypt-xml-elements-with-asymmetric-keys.md)
