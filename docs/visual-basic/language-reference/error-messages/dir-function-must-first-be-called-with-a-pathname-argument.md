---
title: 必须首先用一个“PathName”自变量调用“Dir”函数
ms.date: 07/20/2015
f1_keywords:
- vbrDIR_IllegalCall
ms.assetid: 7b5d149f-be91-4ac3-8262-86a360894e7d
ms.openlocfilehash: 828c715d9aaceef17d030113e7eda302f025ca9d
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/30/2019
ms.locfileid: "55282579"
---
# <a name="dir-function-must-first-be-called-with-a-pathname-argument"></a>必须首先用一个“PathName”自变量调用“Dir”函数
首次调用`Dir`函数不包括`PathName`参数。 首次调用`Dir`必须包含`PathName`，但后续调用`Dir`无需包含参数来检索下一项。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
1.  提供`PathName`函数调用中的参数。  
  
## <a name="see-also"></a>请参阅
- <xref:Microsoft.VisualBasic.FileSystem.Dir%2A>
