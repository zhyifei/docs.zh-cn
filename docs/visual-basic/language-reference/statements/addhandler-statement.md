---
title: AddHandler 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 6ed6f3d4fd77d714ab554d641c0c0fc4f403bbf8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54715096"
---
# <a name="addhandler-statement"></a>AddHandler 语句
在运行时将事件与事件处理程序。  
  
## <a name="syntax"></a>语法  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>部件  
|||
|---|---|
|Event — 事件|要处理的事件的名称。|  
|`eventhandler`|处理事件的过程的名称。|
|||
  
## <a name="remarks"></a>备注  
 `AddHandler`和`RemoveHandler`语句可用于启动和停止事件处理程序执行期间任何时候。  
  
 签名`eventhandler`过程必须与该事件的签名匹配`event`。  
  
 `Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。 `AddHandler` 语句在运行时将过程连接到事件。 定义过程时使用 `Handles` 关键字，以指定它处理特定事件。 有关详细信息，请参阅[处理](../../../visual-basic/language-reference/statements/handles-clause.md)。  
  
> [!NOTE]
>  用于自定义事件`AddHandler`语句调用事件的`AddHandler`访问器。 自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅
- [RemoveHandler 语句](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)
- [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
