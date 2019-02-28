---
title: 加密和解密在 Visual Basic 中的字符串
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: fe91e0062ac35859a3b85eb080d16fb88a6f9aaf
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/28/2019
ms.locfileid: "56972776"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="800f8-102">演练：加密和解密在 Visual Basic 中的字符串</span><span class="sxs-lookup"><span data-stu-id="800f8-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="800f8-103">本演练演示如何使用<xref:System.Security.Cryptography.DESCryptoServiceProvider>类来加密和解密使用加密服务提供程序 (CSP) 版本的三重数据加密标准字符串 (<xref:System.Security.Cryptography.TripleDES>) 算法。</span><span class="sxs-lookup"><span data-stu-id="800f8-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="800f8-104">第一步是创建一个简单的包装器类，它封装 3DES 算法，并将加密的数据存储为 base-64 编码字符串。</span><span class="sxs-lookup"><span data-stu-id="800f8-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="800f8-105">然后，该包装器用于安全地存储在可公开访问的文本文件中的私有用户数据。</span><span class="sxs-lookup"><span data-stu-id="800f8-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="800f8-106">可以使用加密来保护用户机密 （例如，密码） 并使凭据未经授权的用户不可读。</span><span class="sxs-lookup"><span data-stu-id="800f8-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="800f8-107">这样可防止授权的用户的标识从被盗，可保护用户的资产，并提供不可否认性。</span><span class="sxs-lookup"><span data-stu-id="800f8-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="800f8-108">加密还可以保护用户的数据不被未经授权的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="800f8-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="800f8-109">有关更多信息，请参阅[加密服务](../../../../standard/security/cryptographic-services.md)。</span><span class="sxs-lookup"><span data-stu-id="800f8-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="800f8-110">Rijndael （现在称为高级加密标准 [AES]） 和三重数据加密标准 (3DES) 算法提供更高的安全性比 DES，因为它们是多个计算密集型操作。</span><span class="sxs-lookup"><span data-stu-id="800f8-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="800f8-111">有关详细信息，请参阅 <xref:System.Security.Cryptography.DES> 和 <xref:System.Security.Cryptography.Rijndael>。</span><span class="sxs-lookup"><span data-stu-id="800f8-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="800f8-112">若要创建加密包装器</span><span class="sxs-lookup"><span data-stu-id="800f8-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="800f8-113">创建`Simple3Des`类来封装的加密和解密的方法。</span><span class="sxs-lookup"><span data-stu-id="800f8-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2.  <span data-ttu-id="800f8-114">将加密命名空间的导入语句添加到包含文件的开始`Simple3Des`类。</span><span class="sxs-lookup"><span data-stu-id="800f8-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3.  <span data-ttu-id="800f8-115">在`Simple3Des`类中，添加一个私有字段以存储 3DES 加密服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="800f8-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4.  <span data-ttu-id="800f8-116">添加一个私有方法创建一个指定长度的字节数组从指定键的哈希。</span><span class="sxs-lookup"><span data-stu-id="800f8-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5.  <span data-ttu-id="800f8-117">添加构造函数初始化 3DES 加密服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="800f8-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="800f8-118">`key`参数控制`EncryptData`和`DecryptData`方法。</span><span class="sxs-lookup"><span data-stu-id="800f8-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6.  <span data-ttu-id="800f8-119">添加对字符串进行加密的公共方法。</span><span class="sxs-lookup"><span data-stu-id="800f8-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7.  <span data-ttu-id="800f8-120">添加对字符串进行解密的公共方法。</span><span class="sxs-lookup"><span data-stu-id="800f8-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="800f8-121">现在可以使用包装类，保护用户的资产。</span><span class="sxs-lookup"><span data-stu-id="800f8-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="800f8-122">在此示例中，它用于安全地存储在可公开访问的文本文件中的私有用户数据。</span><span class="sxs-lookup"><span data-stu-id="800f8-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="800f8-123">若要测试加密包装器</span><span class="sxs-lookup"><span data-stu-id="800f8-123">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="800f8-124">在单独的类中，添加一个方法来使用包装器的`EncryptData`方法对字符串进行加密并将其写入到用户的我的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="800f8-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2.  <span data-ttu-id="800f8-125">添加从用户中读取加密的字符串的方法的我的文档文件夹，并解密使用包装器的字符串`DecryptData`方法。</span><span class="sxs-lookup"><span data-stu-id="800f8-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3.  <span data-ttu-id="800f8-126">添加用户界面代码来调用`TestEncoding`和`TestDecoding`方法。</span><span class="sxs-lookup"><span data-stu-id="800f8-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="800f8-127">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="800f8-127">Run the application.</span></span>  
  
     <span data-ttu-id="800f8-128">测试应用程序时，请注意，它将解密数据，是否提供了错误的密码。</span><span class="sxs-lookup"><span data-stu-id="800f8-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="800f8-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="800f8-129">See also</span></span>
- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="800f8-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="800f8-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
