---
title: '&#39; Dir &#39;函数必须首先调用与 &#39;路径名 &#39;自变量'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
caps.latest.revision: 7
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 843918fe9cb0b9dece076b5dc1373c3571588caa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="39dir39-function-must-first-be-called-with-a-39pathname39-argument"></a>&#39; Dir &#39;函数必须首先调用与 &#39;路径名 &#39;自变量
首次调用`Dir`函数不包括`PathName`自变量。 首次调用`Dir`必须包括`PathName`，但后续调用`Dir`不需要包括参数，以便检索下一项。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  提供`PathName`函数调用中的自变量。  
  
## <a name="see-also"></a>另请参阅  
 <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
