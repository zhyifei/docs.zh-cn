---
title: "RemoveHandler 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 82d130c6536df7d72977a028333293b4e0ee89de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
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
  
## <a name="see-also"></a>另请参阅  
 [AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
 [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
