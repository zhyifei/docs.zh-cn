---
title: GetType Operator
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 4e59bcfaa24c9545ed75c6b5c1d29cad398ac2de
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349553"
---
# <a name="gettype-operator-visual-basic"></a>GetType 运算符 (Visual Basic)
返回指定类型的 <xref:System.Type> 对象。 <xref:System.Type> 对象提供有关类型的信息，如其属性、方法和事件。  
  
## <a name="syntax"></a>语法  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a>参数  
  
|参数|说明|  
|---|---|  
|`typename`|要获取其信息的类型的名称。|  
  
## <a name="remarks"></a>备注  
 `GetType` 运算符返回指定 `typename`的 <xref:System.Type> 对象。 可以在 `typename`中传递任何已定义类型的名称。 这包括：  
  
- 任何 Visual Basic 数据类型，如 `Boolean` 或 `Date`。  
  
- 任何 .NET Framework 类、结构、模块或接口，如 <xref:System.ArgumentException?displayProperty=nameWithType> 或 <xref:System.Double?displayProperty=nameWithType>。  
  
- 应用程序定义的任何类、结构、模块或接口。  
  
- 应用程序定义的任何数组。  
  
- 应用程序定义的任何委托。  
  
- Visual Basic、.NET Framework 或应用程序定义的任何枚举。  
  
 如果要获取对象变量的类型对象，请使用 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 方法。  
  
 在以下情况下，`GetType` 运算符可能很有用：  
  
- 您必须在运行时访问类型的元数据。 <xref:System.Type> 对象提供了元数据，例如类型成员和部署信息。 例如，您需要这样做来反映程序集。 有关详细信息，请参阅 <xref:System.Reflection?displayProperty=nameWithType>。  
  
- 要比较两个对象引用，以确定它们是否引用相同类型的实例。 如果是这样，`GetType` 将返回对同一 <xref:System.Type> 对象的引用。  
  
## <a name="example"></a>示例  
 下面的示例演示了使用中的 `GetType` 运算符。  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a>另请参阅

- [Visual Basic 中的运算符优先级](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [按功能列出的运算符](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [运算符和表达式](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
