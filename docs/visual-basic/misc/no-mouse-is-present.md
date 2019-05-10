---
title: 没有鼠标
ms.date: 07/20/2015
f1_keywords:
- vbrMouse_NoMouseIsPresent
ms.assetid: 4472fd57-4217-4463-9d3c-dc4a8fe88f1b
ms.openlocfilehash: 5493cea8c87a40b0c9663aaa7f36ce6cb423d346
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64624865"
---
# <a name="no-mouse-is-present"></a>没有鼠标
调用了 `My.Computer.Mouse` 对象的一个属性，但是计算机未安装鼠标或鼠标端口。  
  
## <a name="to-correct-this-error"></a>更正此错误  
  
- 在调用周围将 `Try...Catch` 块添加到 `My.Computer.Mouse` 对象的属性。  
  
     — 或 —  
  
- 在计算机上安装鼠标。  
  
## <a name="see-also"></a>请参阅

- [My.Computer.Mouse](xref:Microsoft.VisualBasic.Devices.Mouse)
- [在 .NET 中处理和引发异常](../../standard/exceptions/index.md)
- [Try...Catch...Finally 语句](../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
