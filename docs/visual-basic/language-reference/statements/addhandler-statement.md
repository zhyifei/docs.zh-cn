---
title: "AddHandler 语句"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords: AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
caps.latest.revision: "15"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 07fbfe04ccd01b7d0f99338ef2682238830099dc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="addhandler-statement"></a>AddHandler 语句
将事件与事件处理程序关联在运行时。  
  
## <a name="syntax"></a>语法  
  
```  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>部件  
 `event`  
 要处理的事件名称。  
  
 `eventhandler`  
 处理事件的过程的名称。  
  
## <a name="remarks"></a>备注  
 `AddHandler`和`RemoveHandler`语句使您可以启动和停止程序执行期间的任何时候的事件处理。  
  
 签名`eventhandler`过程必须与匹配的事件的签名`event`。  
  
 `Handles` 关键字和 `AddHandler` 语句都允许你指定特定过程处理特定事件，但存在差异。 `AddHandler` 语句在运行时将过程连接到事件。 定义过程时使用 `Handles` 关键字，以指定它处理特定事件。 有关详细信息，请参阅[处理](../../../visual-basic/language-reference/statements/handles-clause.md)。  
  
> [!NOTE]
>  对于自定义事件，`AddHandler`语句调用事件的`AddHandler`访问器。 有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrEvents#17](../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/addhandler-statement_1.vb)]  
  
## <a name="see-also"></a>另请参阅  
 [RemoveHandler 语句](../../../visual-basic/language-reference/statements/removehandler-statement.md)  
 [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)  
 [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)  
 [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
