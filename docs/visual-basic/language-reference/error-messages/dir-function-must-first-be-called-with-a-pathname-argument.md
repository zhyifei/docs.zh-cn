---
title: '&#39;Dir&#39;函数必须首先调用与&#39;路径名&#39;自变量'
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 3a271d7c2c2f7b98bae8f3f6fa9b67b65e3548f9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33585455"
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39;Dir&#39;函数必须首先调用与&#39;路径名&#39;自变量
首次调用`Dir`函数不包括`PathName`自变量。 首次调用`Dir`必须包括`PathName`，但后续调用`Dir`不需要包括参数，以便检索下一项。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  提供`PathName`函数调用中的自变量。  
  
## <a name="see-also"></a>请参阅  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
