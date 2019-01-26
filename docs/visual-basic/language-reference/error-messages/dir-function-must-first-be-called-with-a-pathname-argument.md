---
title: '&#39;Dir&#39;函数必须首先调用使用&#39;PathName&#39;参数'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: f7e9ef9cc6309f24ae9f8963e910b41180c029b7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518483"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39;Dir&#39;函数必须首先调用使用&#39;PathName&#39;参数
首次调用`Dir`函数不包括`PathName`参数。 首次调用`Dir`必须包含`PathName`，但后续调用`Dir`无需包含参数来检索下一项。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  提供`PathName`函数调用中的参数。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
