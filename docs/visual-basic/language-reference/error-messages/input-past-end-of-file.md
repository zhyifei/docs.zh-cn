---
title: 输入超出文件尾
ms.date: 07/20/2015
f1_keywords:
- vbrID62
ms.assetid: 65292704-6e7d-4622-9f50-eb655a59b016
ms.openlocfilehash: 29a9b5ce3c3f8e6a02b52beda1338fd699143570
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54491332"
---
# <a name="input-past-end-of-file"></a>输入超出文件尾
任一`Input`语句正在读取的文件为空或其中的所有数据都使用，或者您都使用`EOF`函数和一个文件打开以进行二进制访问。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  使用`EOF`函数之前`Input`语句，以检测到文件末尾。  
  
2.  如果为进行二进制访问打开该文件，则使用`Seek`和`Loc`。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.FileSystem.Input%2A>
- <xref:Microsoft.VisualBasic.FileSystem.EOF%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Seek%2A>
- <xref:Microsoft.VisualBasic.FileSystem.Loc%2A>
