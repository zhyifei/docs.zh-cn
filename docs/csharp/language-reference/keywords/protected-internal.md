---
title: "受保护内部 （C# 参考）"
ms.date: 11/15/2017
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
author: sputier
ms.author: wiwagn
ms.openlocfilehash: f9004a5e8d65179c9ff2e30688e63c14c95ab431
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="protected-internal-c-reference"></a>受保护内部 （C# 参考）
`protected internal`关键字组合都是成员访问修饰符。 受保护的内部成员是从当前程序集或从包含类派生的类型访问。 有关 `protected internal` 和其他访问修饰符的比较，请参阅[可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)。 
   
## <a name="example"></a>示例  
 可从其包含的程序集内的任何类型的基类的受保护内部成员进行访问。 它也是位于另一个程序集中，仅当访问是通过派生的类类型的变量的派生类中可访问的。 以下面的代码段为例：  

```
// Assembly1.cs  
// Compile with: /target:library  
public class BaseClass   
{  
   protected internal int myValue = 0;  
}

class TestAccess 
{
    void Access()
    {
        BaseClass baseObject = new BaseClass();
        baseObject.myValue = 5;
    }
}  
```  
  
```  
// Assembly2.cs  
// Compile with: /reference:Assembly1.dll  
class DerivedClass : BaseClass   
{  
    static void Main()
    {
        BaseClass baseObject = new BaseClass();
        DerivedClass derivedObject = new DerivedClass();

        // Error CS1540, because myValue can only be accessed by
        // classes derived from BaseClass.
        // baseObject.myValue = 10; 

        // OK, because this class derives from BaseClass.
        derivedObject.myValue = 10;
    }
} 
```  
 此示例包含两个文件，即 `Assembly1.cs` 和 `Assembly2.cs`。 第一个文件包含公共的基类， `BaseClass`，和另一个类， `TestAccess`。 `BaseClass`拥有受保护的内部成员， `myValue`，这可通过`TestAccess`类型。 在第二个文件中，尝试访问`myValue`的实例通过`BaseClass`将产生错误，对派生类的实例通过此成员的访问权限时`DerivedClass`将会成功。 

 结构成员不能为`protected internal`由于结构不能被继承。  
  
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)   
 [C# 编程指南](../../../csharp/programming-guide/index.md)   
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)   
 [访问修饰符](../../../csharp/language-reference/keywords/access-modifiers.md)   
 [可访问性级别](../../../csharp/language-reference/keywords/accessibility-levels.md)   
 [修饰符](../../../csharp/language-reference/keywords/modifiers.md)   
 [public](../../../csharp/language-reference/keywords/public.md)   
 [private](../../../csharp/language-reference/keywords/private.md)   
 [internal](../../../csharp/language-reference/keywords/internal.md)   
 [Internal virtual 关键字的安全问题](https://msdn.microsoft.com/library/heyd8kky(v=vs.110))
