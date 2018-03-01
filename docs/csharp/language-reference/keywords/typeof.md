---
title: "typeof（C# 参考）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- typeof
- typeof_CSharpKeyword
helpviewer_keywords:
- typeof keyword [C#]
ms.assetid: 0c08d880-515e-46bb-8cd2-48b8dd62c08d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: be24740ea7f6fbe8780dd9cac58b7dea9aaf6872
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="typeof-c-reference"></a>typeof（C# 参考）
用于为类型获取 `System.Type` 对象。 `typeof` 表达式采用以下格式：  
  
```  
System.Type type = typeof(int);  
```  
  
## <a name="remarks"></a>备注  
 若要获取表达式的运行时类型，可以使用 .NET Framework 方法 <xref:System.Object.GetType%2A>，如以下示例所示：  
  
```  
int i = 0;  
System.Type type = i.GetType();  
```  
  
 不能重载 `typeof` 运算符。  
  
 `typeof` 运算符也可用于开放式泛型类型。 具有多个类型参数的类型必须在规范中具有适当数量的逗号。 以下示例显示如何确定方法的返回类型是否为泛型 <xref:System.Collections.Generic.IEnumerable%601>。 假设该方法是 MethodInfo 类型的实例：  
  
```  
string s = method.ReturnType.GetInterface  
    (typeof(System.Collections.Generic.IEnumerable<>).FullName);  
```  
  
## <a name="example"></a>示例  
 [!code-csharp[csrefKeywordsOperator#12](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_1.cs)]  
  
## <a name="example"></a>示例  
 此示例使用 <xref:System.Object.GetType%2A> 方法来确定用于包含数值计算结果的类型。 这取决于所得数字的存储要求。  
  
 [!code-csharp[csrefKeywordsOperator#13](../../../csharp/language-reference/keywords/codesnippet/CSharp/typeof_2.cs)]  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>另请参阅  
 <xref:System.Type?displayProperty=nameWithType>  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [is](../../../csharp/language-reference/keywords/is.md)  
 [运算符关键字](../../../csharp/language-reference/keywords/operator-keywords.md)
