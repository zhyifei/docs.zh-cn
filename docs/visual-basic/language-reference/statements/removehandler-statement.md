---
title: RemoveHandler 语句 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.RemoveHandlerMethod
- vb.RemoveHandler
- RemoveHandler
helpviewer_keywords:
- RemoveHandler keyword [Visual Basic]
- RemoveHandler statement [Visual Basic]
ms.assetid: 647cd825-e877-4910-b4f1-8d168beebe6a
ms.openlocfilehash: 3a839a7d05d05066f6c0f774a683c8fc83c19643
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957723"
---
# <a name="removehandler-statement"></a>RemoveHandler 语句
删除事件和事件处理程序之间的关联。  
  
## <a name="syntax"></a>语法  
  
```  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>部件  
  
|术语|定义|  
|---|---|  
|`event`|正在处理的事件的名称。|  
|`eventhandler`|当前处理事件的过程的名称。|  
  
## <a name="remarks"></a>备注  
 使用`AddHandler` 和`RemoveHandler`语句, 可以在程序执行过程中随时启动和停止特定事件的事件处理。  
  
> [!NOTE]
> 对于自定义事件, `RemoveHandler`该语句将调用事件`RemoveHandler`的访问器。 有关自定义事件的详细信息, 请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>请参阅

- [AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)
- [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
