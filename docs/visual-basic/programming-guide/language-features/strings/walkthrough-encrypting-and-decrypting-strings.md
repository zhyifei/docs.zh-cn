---
title: "加密和解密在 Visual Basic 中的字符串"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: fd9ec8e7af771db3f042e08c8ab30f6ed5832c2b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="27bee-102">演练：在 Visual Basic 中对字符串进行加密和解密</span><span class="sxs-lookup"><span data-stu-id="27bee-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="27bee-103">本演练演示如何使用<xref:System.Security.Cryptography.DESCryptoServiceProvider>类进行加密和解密使用三重数据加密标准的加密服务提供程序 (CSP) 版本字符串 (<xref:System.Security.Cryptography.TripleDES>) 算法。</span><span class="sxs-lookup"><span data-stu-id="27bee-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="27bee-104">第一步是创建一个简单的包装类，封装 3DES 算法，并将加密的数据存储为 base 64 编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="27bee-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="27bee-105">然后，该包装用于安全地将私人用户数据存储在可公开访问的文本文件。</span><span class="sxs-lookup"><span data-stu-id="27bee-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="27bee-106">你可以使用加密保护用户的机密信息 （例如，密码） 和以使未经授权的用户的凭据不可读。</span><span class="sxs-lookup"><span data-stu-id="27bee-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="27bee-107">这样可防止授权的用户的标识从此被盗用、 用于保护用户的资源，并提供不可否认性。</span><span class="sxs-lookup"><span data-stu-id="27bee-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="27bee-108">加密还可以保护不被未经授权的用户的访问的用户的数据。</span><span class="sxs-lookup"><span data-stu-id="27bee-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="27bee-109">有关详细信息，请参阅[加密服务](../../../../standard/security/cryptographic-services.md)。</span><span class="sxs-lookup"><span data-stu-id="27bee-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="27bee-110">Rijndael （现在称为高级加密标准 [AES]） 和三重数据加密标准 (3DES) 算法提供比 DES 更为安全，因为它们是多个计算密集型操作。</span><span class="sxs-lookup"><span data-stu-id="27bee-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="27bee-111">有关详细信息，请参阅 <xref:System.Security.Cryptography.DES> 和 <xref:System.Security.Cryptography.Rijndael>。</span><span class="sxs-lookup"><span data-stu-id="27bee-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="27bee-112">若要创建加密包装器</span><span class="sxs-lookup"><span data-stu-id="27bee-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="27bee-113">创建`Simple3Des`类来封装的加密和解密的方法。</span><span class="sxs-lookup"><span data-stu-id="27bee-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  <span data-ttu-id="27bee-114">将加密命名空间的导入语句添加到包含文件的开头`Simple3Des`类。</span><span class="sxs-lookup"><span data-stu-id="27bee-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  <span data-ttu-id="27bee-115">在`Simple3Des`类中，添加一个私有字段以存储 3DES 加密服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="27bee-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  <span data-ttu-id="27bee-116">添加一个私有方法创建从指定的键的哈希指定长度的字节数组。</span><span class="sxs-lookup"><span data-stu-id="27bee-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  <span data-ttu-id="27bee-117">添加一个构造函数来初始化 3DES 加密服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="27bee-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="27bee-118">`key`参数控件`EncryptData`和`DecryptData`方法。</span><span class="sxs-lookup"><span data-stu-id="27bee-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  <span data-ttu-id="27bee-119">添加一个公共方法，对字符串进行加密。</span><span class="sxs-lookup"><span data-stu-id="27bee-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  <span data-ttu-id="27bee-120">添加对字符串进行解密的公共方法。</span><span class="sxs-lookup"><span data-stu-id="27bee-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     <span data-ttu-id="27bee-121">包装类现在可以用于保护用户资产。</span><span class="sxs-lookup"><span data-stu-id="27bee-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="27bee-122">在此示例中，它用于安全地将私人用户数据存储在可公开访问的文本文件。</span><span class="sxs-lookup"><span data-stu-id="27bee-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="27bee-123">若要测试加密包装器</span><span class="sxs-lookup"><span data-stu-id="27bee-123">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="27bee-124">在单独的类中，添加一个方法来使用包装器的`EncryptData`方法加密字符串并将其写入到用户的我的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="27bee-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  <span data-ttu-id="27bee-125">添加从用户读取加密的字符串的方法的我的文档文件夹，并解密使用包装器的字符串`DecryptData`方法。</span><span class="sxs-lookup"><span data-stu-id="27bee-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  <span data-ttu-id="27bee-126">添加用户界面代码来调用`TestEncoding`和`TestDecoding`方法。</span><span class="sxs-lookup"><span data-stu-id="27bee-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="27bee-127">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="27bee-127">Run the application.</span></span>  
  
     <span data-ttu-id="27bee-128">当你测试应用程序时，请注意它将解密数据，是否你提供了错误的密码。</span><span class="sxs-lookup"><span data-stu-id="27bee-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27bee-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="27bee-129">See Also</span></span>  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [<span data-ttu-id="27bee-130">加密服务</span><span class="sxs-lookup"><span data-stu-id="27bee-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
