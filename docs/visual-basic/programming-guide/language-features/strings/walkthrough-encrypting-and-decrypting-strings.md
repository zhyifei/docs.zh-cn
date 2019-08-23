---
title: 对 Visual Basic 中的字符串进行加密和解密
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: ee8691fedb537d1aa588eaac61624b445da64d1f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69944430"
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a><span data-ttu-id="db3c0-102">演练：对 Visual Basic 中的字符串进行加密和解密</span><span class="sxs-lookup"><span data-stu-id="db3c0-102">Walkthrough: Encrypting and Decrypting Strings in Visual Basic</span></span>
<span data-ttu-id="db3c0-103">本演练演示了如何使用<xref:System.Security.Cryptography.DESCryptoServiceProvider>类, 通过使用三重数据加密标准 (<xref:System.Security.Cryptography.TripleDES>) 算法的加密服务提供程序 (CSP) 版本来对字符串进行加密和解密。</span><span class="sxs-lookup"><span data-stu-id="db3c0-103">This walkthrough shows you how to use the <xref:System.Security.Cryptography.DESCryptoServiceProvider> class to encrypt and decrypt strings using the cryptographic service provider (CSP) version of the Triple Data Encryption Standard (<xref:System.Security.Cryptography.TripleDES>) algorithm.</span></span> <span data-ttu-id="db3c0-104">第一步是创建一个封装3DES 算法的简单包装器类, 并将加密数据存储为64编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="db3c0-104">The first step is to create a simple wrapper class that encapsulates the 3DES algorithm and stores the encrypted data as a base-64 encoded string.</span></span> <span data-ttu-id="db3c0-105">然后, 使用该包装将私有用户数据安全地存储在可公开访问的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="db3c0-105">Then, that wrapper is used to securely store private user data in a publicly accessible text file.</span></span>  
  
 <span data-ttu-id="db3c0-106">你可以使用加密来保护用户机密 (例如密码), 并使凭据不受未经授权的用户读取。</span><span class="sxs-lookup"><span data-stu-id="db3c0-106">You can use encryption to protect user secrets (for example, passwords) and to make credentials unreadable by unauthorized users.</span></span> <span data-ttu-id="db3c0-107">这可以防止授权用户的身份被盗, 从而保护用户的资产并提供不可否认性。</span><span class="sxs-lookup"><span data-stu-id="db3c0-107">This can protect an authorized user's identity from being stolen, which protects the user's assets and provides non-repudiation.</span></span> <span data-ttu-id="db3c0-108">加密还可以保护用户的数据, 防止未经授权的用户对其进行访问。</span><span class="sxs-lookup"><span data-stu-id="db3c0-108">Encryption can also protect a user's data from being accessed by unauthorized users.</span></span>  
  
 <span data-ttu-id="db3c0-109">有关更多信息，请参阅[加密服务](../../../../standard/security/cryptographic-services.md)。</span><span class="sxs-lookup"><span data-stu-id="db3c0-109">For more information, see [Cryptographic Services](../../../../standard/security/cryptographic-services.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="db3c0-110">Rijndael (现在称为高级加密标准 [AES]) 和三重数据加密标准 (3DES) 算法提供比 DES 更高的安全性, 因为它们的计算工作量更高。</span><span class="sxs-lookup"><span data-stu-id="db3c0-110">The Rijndael (now referred to as Advanced Encryption Standard [AES]) and Triple Data Encryption Standard (3DES) algorithms provide greater security than DES because they are more computationally intensive.</span></span> <span data-ttu-id="db3c0-111">有关详细信息，请参阅 <xref:System.Security.Cryptography.DES> 和 <xref:System.Security.Cryptography.Rijndael>。</span><span class="sxs-lookup"><span data-stu-id="db3c0-111">For more information, see <xref:System.Security.Cryptography.DES> and <xref:System.Security.Cryptography.Rijndael>.</span></span>  
  
### <a name="to-create-the-encryption-wrapper"></a><span data-ttu-id="db3c0-112">创建加密包装器</span><span class="sxs-lookup"><span data-stu-id="db3c0-112">To create the encryption wrapper</span></span>  
  
1. <span data-ttu-id="db3c0-113">创建用于封装加密和解密方法的类。`Simple3Des`</span><span class="sxs-lookup"><span data-stu-id="db3c0-113">Create the `Simple3Des` class to encapsulate the encryption and decryption methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#38)]  
  
2. <span data-ttu-id="db3c0-114">将加密命名空间的导入添加到包含`Simple3Des`类的文件的开头。</span><span class="sxs-lookup"><span data-stu-id="db3c0-114">Add an import of the cryptography namespace to the start of the file that contains the `Simple3Des` class.</span></span>  
  
     [!code-vb[VbVbalrStrings#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#77)]  
  
3. <span data-ttu-id="db3c0-115">`Simple3Des`在类中, 添加私有字段以存储3des 加密服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="db3c0-115">In the `Simple3Des` class, add a private field to store the 3DES cryptographic service provider.</span></span>  
  
     [!code-vb[VbVbalrStrings#39](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#39)]  
  
4. <span data-ttu-id="db3c0-116">添加一个私有方法, 该方法根据指定键的哈希创建指定长度的字节数组。</span><span class="sxs-lookup"><span data-stu-id="db3c0-116">Add a private method that creates a byte array of a specified length from the hash of the specified key.</span></span>  
  
     [!code-vb[VbVbalrStrings#41](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#41)]  
  
5. <span data-ttu-id="db3c0-117">添加构造函数来初始化3DES 加密服务提供程序。</span><span class="sxs-lookup"><span data-stu-id="db3c0-117">Add a constructor to initialize the 3DES cryptographic service provider.</span></span>  
  
     <span data-ttu-id="db3c0-118">`key`参数控制`DecryptData`和方法。 `EncryptData`</span><span class="sxs-lookup"><span data-stu-id="db3c0-118">The `key` parameter controls the `EncryptData` and `DecryptData` methods.</span></span>  
  
     [!code-vb[VbVbalrStrings#40](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#40)]  
  
6. <span data-ttu-id="db3c0-119">添加加密字符串的公共方法。</span><span class="sxs-lookup"><span data-stu-id="db3c0-119">Add a public method that encrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#42](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#42)]  
  
7. <span data-ttu-id="db3c0-120">添加解密字符串的公共方法。</span><span class="sxs-lookup"><span data-stu-id="db3c0-120">Add a public method that decrypts a string.</span></span>  
  
     [!code-vb[VbVbalrStrings#43](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#43)]  
  
     <span data-ttu-id="db3c0-121">现在可以使用包装类来保护用户资产。</span><span class="sxs-lookup"><span data-stu-id="db3c0-121">The wrapper class can now be used to protect user assets.</span></span> <span data-ttu-id="db3c0-122">在此示例中, 它用于安全地将私有用户数据存储在可公开访问的文本文件中。</span><span class="sxs-lookup"><span data-stu-id="db3c0-122">In this example, it is used to securely store private user data in a publicly accessible text file.</span></span>  
  
### <a name="to-test-the-encryption-wrapper"></a><span data-ttu-id="db3c0-123">测试加密包装器</span><span class="sxs-lookup"><span data-stu-id="db3c0-123">To test the encryption wrapper</span></span>  
  
1. <span data-ttu-id="db3c0-124">在单独的类中, 添加一个方法, 该方法使用`EncryptData`包装器的方法对字符串进行加密并将其写入用户的 "我的文档" 文件夹。</span><span class="sxs-lookup"><span data-stu-id="db3c0-124">In a separate class, add a method that uses the wrapper's `EncryptData` method to encrypt a string and write it to the user's My Documents folder.</span></span>  
  
     [!code-vb[VbVbalrStrings#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#78)]  
  
2. <span data-ttu-id="db3c0-125">添加一个方法, 该方法读取用户的 "我的文档" 文件夹中的加密字符串, 并使用包装`DecryptData`器的方法对字符串进行解密。</span><span class="sxs-lookup"><span data-stu-id="db3c0-125">Add a method that reads the encrypted string from the user's My Documents folder and decrypts the string with the wrapper's `DecryptData` method.</span></span>  
  
     [!code-vb[VbVbalrStrings#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class3.vb#79)]  
  
3. <span data-ttu-id="db3c0-126">添加用户界面代码以调用`TestEncoding`和`TestDecoding`方法。</span><span class="sxs-lookup"><span data-stu-id="db3c0-126">Add user interface code to call the `TestEncoding` and `TestDecoding` methods.</span></span>  
  
4. <span data-ttu-id="db3c0-127">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="db3c0-127">Run the application.</span></span>  
  
     <span data-ttu-id="db3c0-128">在测试应用程序时, 请注意, 如果提供了错误的密码, 它不会对数据进行解密。</span><span class="sxs-lookup"><span data-stu-id="db3c0-128">When you test the application, notice that it will not decrypt the data if you provide the wrong password.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db3c0-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="db3c0-129">See also</span></span>

- <xref:System.Security.Cryptography>
- <xref:System.Security.Cryptography.DESCryptoServiceProvider>
- <xref:System.Security.Cryptography.DES>
- <xref:System.Security.Cryptography.TripleDES>
- <xref:System.Security.Cryptography.Rijndael>
- [<span data-ttu-id="db3c0-130">Cryptographic Services</span><span class="sxs-lookup"><span data-stu-id="db3c0-130">Cryptographic Services</span></span>](../../../../standard/security/cryptographic-services.md)
