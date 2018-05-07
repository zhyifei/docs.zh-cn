---
title: 加密和解密在 Visual Basic 中的字符串
ms.date: 07/20/2015
helpviewer_keywords:
- encryption [Visual Basic], strings
- strings [Visual Basic], encrypting
- decryption [Visual Basic], strings
- strings [Visual Basic], decrypting
ms.assetid: 1f51e40a-2f88-43e2-a83e-28a0b5c0d6fd
ms.openlocfilehash: 96e56ab315a739fef9d5499b076a077f5294f39e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="walkthrough-encrypting-and-decrypting-strings-in-visual-basic"></a>演练：在 Visual Basic 中对字符串进行加密和解密
本演练演示如何使用<xref:System.Security.Cryptography.DESCryptoServiceProvider>类进行加密和解密使用三重数据加密标准的加密服务提供程序 (CSP) 版本字符串 (<xref:System.Security.Cryptography.TripleDES>) 算法。 第一步是创建一个简单的包装类，封装 3DES 算法，并将加密的数据存储为 base 64 编码的字符串。 然后，该包装用于安全地将私人用户数据存储在可公开访问的文本文件。  
  
 你可以使用加密保护用户的机密信息 （例如，密码） 和以使未经授权的用户的凭据不可读。 这样可防止授权的用户的标识从此被盗用、 用于保护用户的资源，并提供不可否认性。 加密还可以保护不被未经授权的用户的访问的用户的数据。  
  
 有关更多信息，请参阅[加密服务](../../../../standard/security/cryptographic-services.md)。  
  
> [!IMPORTANT]
>  Rijndael （现在称为高级加密标准 [AES]） 和三重数据加密标准 (3DES) 算法提供比 DES 更为安全，因为它们是多个计算密集型操作。 有关详细信息，请参阅 <xref:System.Security.Cryptography.DES> 和 <xref:System.Security.Cryptography.Rijndael>。  
  
### <a name="to-create-the-encryption-wrapper"></a>若要创建加密包装器  
  
1.  创建`Simple3Des`类来封装的加密和解密的方法。  
  
     [!code-vb[VbVbalrStrings#38](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_1.vb)]  
  
2.  将加密命名空间的导入语句添加到包含文件的开头`Simple3Des`类。  
  
     [!code-vb[VbVbalrStrings#77](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_2.vb)]  
  
3.  在`Simple3Des`类中，添加一个私有字段以存储 3DES 加密服务提供程序。  
  
     [!code-vb[VbVbalrStrings#39](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_3.vb)]  
  
4.  添加一个私有方法创建从指定的键的哈希指定长度的字节数组。  
  
     [!code-vb[VbVbalrStrings#41](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_4.vb)]  
  
5.  添加一个构造函数来初始化 3DES 加密服务提供程序。  
  
     `key`参数控件`EncryptData`和`DecryptData`方法。  
  
     [!code-vb[VbVbalrStrings#40](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_5.vb)]  
  
6.  添加一个公共方法，对字符串进行加密。  
  
     [!code-vb[VbVbalrStrings#42](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_6.vb)]  
  
7.  添加对字符串进行解密的公共方法。  
  
     [!code-vb[VbVbalrStrings#43](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_7.vb)]  
  
     包装类现在可以用于保护用户资产。 在此示例中，它用于安全地将私人用户数据存储在可公开访问的文本文件。  
  
### <a name="to-test-the-encryption-wrapper"></a>若要测试加密包装器  
  
1.  在单独的类中，添加一个方法来使用包装器的`EncryptData`方法加密字符串并将其写入到用户的我的文档文件夹。  
  
     [!code-vb[VbVbalrStrings#78](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_8.vb)]  
  
2.  添加从用户读取加密的字符串的方法的我的文档文件夹，并解密使用包装器的字符串`DecryptData`方法。  
  
     [!code-vb[VbVbalrStrings#79](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/walkthrough-encrypting-and-decrypting-strings_9.vb)]  
  
3.  添加用户界面代码来调用`TestEncoding`和`TestDecoding`方法。  
  
4.  运行该应用程序。  
  
     当你测试应用程序时，请注意它将解密数据，是否你提供了错误的密码。  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Security.Cryptography>  
 <xref:System.Security.Cryptography.DESCryptoServiceProvider>  
 <xref:System.Security.Cryptography.DES>  
 <xref:System.Security.Cryptography.TripleDES>  
 <xref:System.Security.Cryptography.Rijndael>  
 [加密服务](../../../../standard/security/cryptographic-services.md)
