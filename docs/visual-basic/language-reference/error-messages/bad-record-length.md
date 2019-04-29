---
title: 错误的记录长度
ms.date: 07/20/2015
f1_keywords:
- vbrID59
ms.assetid: 0926a3a4-177b-4452-9b33-d8a01e24cc21
ms.openlocfilehash: 1bc75303bcc2f46e54c06e89347da28997e59786
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61935247"
---
# <a name="bad-record-length"></a>错误的记录长度
此错误的可能原因包括：  
  
- 中指定的记录变量的长度`FileGet`， `FileGetObject`，`FilePut`或`FilePutObject`语句不同于相应中指定的长度`FileOpen`语句。  
  
- 中的变量`FilePut`或`FilePutObject`语句或包含可变长度字符串。  
  
- 中的变量`FilePut`或`FilePutObject`或者包括`Variant`类型。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1. 请确保记录变量的类型定义的用户定义类型中的固定长度变量的大小的总和中声明的值是相同`FileOpen`语句的`Len`子句。  
  
2. 如果中的变量`FilePut`或`FilePutObject`语句或包含可变长度字符串，请确保长度可变的字符串是短于中指定的记录长度至少 2 个字符`Len`子句`FileOpen`语句。  
  
3. 如果中的变量`FilePut`或`FilePutObject`或者包括`Variant`确保可变长度字符串至少 4 个字节长度小于中指定的记录长度`Len`子句`FileOpen`语句。  
  
## <a name="see-also"></a>请参阅

- <xref:Microsoft.VisualBasic.FileSystem.FileGet%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FileGetObject%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePut%2A>
- <xref:Microsoft.VisualBasic.FileSystem.FilePutObject%2A>
