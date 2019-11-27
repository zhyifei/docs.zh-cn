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
ms.openlocfilehash: 177952acf362ccb36a36b5f09b11a1a93dbefa29
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333040"
---
# <a name="removehandler-statement"></a>RemoveHandler 语句
删除事件和事件处理程序之间的关联。  
  
## <a name="syntax"></a>语法  
  
```vb  
RemoveHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>部件  
  
|术语|Definition|  
|---|---|  
|`event`|正在处理的事件的名称。|  
|`eventhandler`|当前处理事件的过程的名称。|  
  
## <a name="remarks"></a>备注  
 使用 `AddHandler` 和 `RemoveHandler` 语句，可以在程序执行过程中随时启动和停止特定事件的事件处理。  
  
> [!NOTE]
> 对于自定义事件，`RemoveHandler` 语句调用事件的 `RemoveHandler` 访问器。 有关自定义事件的详细信息，请参阅[Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)。  
  
## <a name="example"></a>示例  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>另请参阅

- [AddHandler 语句](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [!](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Event 语句](../../../visual-basic/language-reference/statements/event-statement.md)
- [事件](../../../visual-basic/programming-guide/language-features/events/index.md)
