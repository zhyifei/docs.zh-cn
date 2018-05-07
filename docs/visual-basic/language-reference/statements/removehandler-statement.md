---
title: RemoveHandler 语句
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 0d982768707948bd6c616445509e16a462b86f2c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="removehandler-statement"></a>RemoveHandler 语句
删除的事件和事件处理程序之间的关联。  
  
## <a name="syntax"></a>语法  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`event`|正在处理的事件的名称。|  
|`eventhandler`|当前正在处理该事件过程的名称。|  
  
## <a name="remarks"></a>备注  
 `AddHandler`和`RemoveHandler`语句使您可以启动和停止程序执行期间随时特定事件的事件处理。  
  
> [!NOTE]
>  对于自定义事件，`RemoveHandler`语句调用事件的`RemoveHandler`访问器。 有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/removehandler-statement_1.vb)]  
  
## <a name="see-also"></a>请参阅  
 [AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
 [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
