---
title: "加密和解密在 Visual Basic 中的字符串 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- encryption, strings
- strings [Visual Basic], encrypting
- decryption, strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 460b0e6e84f5be23f0c811e48daf36d3d4af3d23
ms.contentlocale: zh-cn
ms.lasthandoff: 04/12/2017

---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="0c5ae-102">演练：在 Visual Basic 中对字符串进行加密和解密</span><span class="sxs-lookup"><span data-stu-id="0c5ae-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="0c5ae-103">本演练演示如何使用<xref:System.Security.Cryptography.DESCryptoServiceProvider>类来加密和解密使用加密服务提供程序 (CSP) 版本的三重数据加密标准字符串 (<xref:System.Security.Cryptography.TripleDES>) 算法。</xref:System.Security.Cryptography.TripleDES> </xref:System.Security.Cryptography.DESCryptoServiceProvider></span><span class="sxs-lookup"><span data-stu-id="0c5ae-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="0c5ae-104">第一步是创建一个简单的包装类，它封装 3DES 算法，并将已加密的数据存储为 base 64 编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="0c5ae-105">然后，该包装用于安全地将私人用户数据存储在可公开访问的文本文件。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="0c5ae-106">可以使用加密来保护用户的机密信息 （如密码） 并进行未经授权的用户无法读取凭据。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="0c5ae-107">这样可防止授权的用户的标识从此被盗用、 它保护用户的资产并提供不可否认性。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="0c5ae-108">加密还可保护用户的数据不被未经授权的用户的访问。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="0c5ae-109">有关详细信息，请参阅[加密服务](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-109">For more information, see [Cryptographic Services](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="0c5ae-110">Rijndael （现在称为高级加密标准 [AES]） 和三重数据加密标准 (3DES) 算法提供更高的安全性比 DES，因为它们是多个计算密集型操作。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="0c5ae-111">有关详细信息，请参阅<xref:System.Security.Cryptography.DES>和<xref:System.Security.Cryptography.Rijndael>。</xref:System.Security.Cryptography.Rijndael> </xref:System.Security.Cryptography.DES></span><span class="sxs-lookup"><span data-stu-id="0c5ae-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="0c5ae-112">若要创建加密包装器</span><span class="sxs-lookup"><span data-stu-id="0c5ae-112">To create the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="0c5ae-113">创建`Simple3Des`类来封装的加密和解密的方法。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     <span data-ttu-id="0c5ae-114">[!code-vb[VbVbalrStrings #&38;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-114">[!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]</span></span>  
  
2.  <span data-ttu-id="0c5ae-115">将加密命名空间导入添加到包含的文件的起始位置`Simple3Des`类。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-115">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     <span data-ttu-id="0c5ae-116">[!code-vb[VbVbalrStrings #&77;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-116">[!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]</span></span>  
  
3.  <span data-ttu-id="0c5ae-117">在`Simple3Des`类，添加一个私有字段来存储 3DES 加密服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-117">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="0c5ae-118">[!code-vb[VbVbalrStrings #&39;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-118">[!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]</span></span>  
  
4.  <span data-ttu-id="0c5ae-119">添加一个从指定的键的哈希值创建一个指定长度的字节数组的私有方法。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-119">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     <span data-ttu-id="0c5ae-120">[!code-vb[VbVbalrStrings #&41;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-120">[!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]</span></span>  
  
5.  <span data-ttu-id="0c5ae-121">添加一个构造函数来初始化 3DES 加密服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-121">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="0c5ae-122">`key`参数控制`EncryptData`和`DecryptData`方法。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-122">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     <span data-ttu-id="0c5ae-123">[!code-vb[VbVbalrStrings #&40;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-123">[!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]</span></span>  
  
6.  <span data-ttu-id="0c5ae-124">添加对字符串进行加密的公共方法。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-124">Add a public method that encrypts a string.</span></span>  
  
     <span data-ttu-id="0c5ae-125">[!code-vb[VbVbalrStrings #&42;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-125">[!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]</span></span>  
  
7.  <span data-ttu-id="0c5ae-126">添加对字符串进行解密的公共方法。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-126">Add a public method that decrypts a string.</span></span>  
  
     <span data-ttu-id="0c5ae-127">[!code-vb[VbVbalrStrings #&43;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-127">[!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]</span></span>  
  
     <span data-ttu-id="0c5ae-128">包装类现在可以用于保护用户的资产。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-128">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="0c5ae-129">在本示例中，它用于安全地将私人用户数据存储在可公开访问的文本文件。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-129">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="0c5ae-130">若要测试加密包装器</span><span class="sxs-lookup"><span data-stu-id="0c5ae-130">To test the encryption wrapper</span></span>  
  
1.  <span data-ttu-id="0c5ae-131">在单独的类中，添加一个方法来使用该包装`EncryptData`方法加密字符串，并将其写入到用户的我的文档文件夹。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-131">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     <span data-ttu-id="0c5ae-132">[!code-vb[VbVbalrStrings #&78;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-132">[!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]</span></span>  
  
2.  <span data-ttu-id="0c5ae-133">添加从用户读取加密的字符串的方法的我的文档文件夹并使用包装器的字符串解密`DecryptData`方法。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-133">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     <span data-ttu-id="0c5ae-134">[!code-vb[VbVbalrStrings #&79;](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="0c5ae-134">[!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]</span></span>  
  
3.  <span data-ttu-id="0c5ae-135">添加用户界面代码以调用`TestEncoding`和`TestDecoding`方法。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-135">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4.  <span data-ttu-id="0c5ae-136">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-136">Run the application.</span></span>  
  
     <span data-ttu-id="0c5ae-137">测试应用程序时，请注意它将解密的数据，是否提供了错误的密码。</span><span class="sxs-lookup"><span data-stu-id="0c5ae-137">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c5ae-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0c5ae-138">See Also</span></span>  
 <span data-ttu-id="0c5ae-139"><xref:System.Security.Cryptography></xref:System.Security.Cryptography></span><span class="sxs-lookup"><span data-stu-id="0c5ae-139"><xref:System.Security.Cryptography></span></span>   
 <span data-ttu-id="0c5ae-140"><xref:System.Security.Cryptography.DESCryptoServiceProvider></xref:System.Security.Cryptography.DESCryptoServiceProvider></span><span class="sxs-lookup"><span data-stu-id="0c5ae-140"><xref:System.Security.Cryptography.DESCryptoServiceProvider></span></span>   
 <span data-ttu-id="0c5ae-141"><xref:System.Security.Cryptography.DES></xref:System.Security.Cryptography.DES></span><span class="sxs-lookup"><span data-stu-id="0c5ae-141"><xref:System.Security.Cryptography.DES></span></span>   
 <span data-ttu-id="0c5ae-142"><xref:System.Security.Cryptography.TripleDES></xref:System.Security.Cryptography.TripleDES></span><span class="sxs-lookup"><span data-stu-id="0c5ae-142"><xref:System.Security.Cryptography.TripleDES></span></span>   
 <span data-ttu-id="0c5ae-143"><xref:System.Security.Cryptography.Rijndael></xref:System.Security.Cryptography.Rijndael></span><span class="sxs-lookup"><span data-stu-id="0c5ae-143"><xref:System.Security.Cryptography.Rijndael></span></span>   
<span data-ttu-id="0c5ae-144"> [加密服务](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)</span><span class="sxs-lookup"><span data-stu-id="0c5ae-144"> [Cryptographic Services](http://msdn.microsoft.com/library/f96284bc-7b73-44b5-ac59-fac613ad09f8)</span></span>
