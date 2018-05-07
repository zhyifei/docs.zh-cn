---
title: 属性 (F#)
description: '了解有关 F # 属性，哪些是表示与对象相关联的值的成员。'
ms.date: 05/16/2016
ms.openlocfilehash: 7aa71b1801b44fedcb420b824078004c6c240dc2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="properties"></a>属性

*属性*表示与对象相关联的值的成员。


## <a name="syntax"></a>语法

```fsharp
// Property that has both get and set defined.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with [accessibility-modifier] get() =
    get-function-body
and [accessibility-modifier] set parameter =
    set-function-body

// Alternative syntax for a property that has get and set.
[ attributes-for-get ]
[ static ] member [accessibility-modifier-for-get] [self-identifier.]PropertyName =
    get-function-body
[ attributes-for-set ]
[ static ] member [accessibility-modifier-for-set] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName =
    get-function-body

// Alternative syntax for property that has get only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with get() =
    get-function-body

// Property that has set only.
[ attributes ]
[ static ] member [accessibility-modifier] [self-identifier.]PropertyName
with set parameter =
    set-function-body

// Automatically implemented properties.
[ attributes ]
[ static ] member val [accessibility-modifier] PropertyName = initialization-expression [ with get, set ]
```

## <a name="remarks"></a>备注
属性表示"具有"在面向对象编程中，表示与对象实例，或对于静态属性，与类型关联的数据的关系。

你可以声明两种方式，具体取决于是否想要 （也称为后备存储） 的基础值显式指定的属性，或如果你想要允许编译器自动生成你的后备存储的属性。 通常情况下，你应使用的更明确的方式，如果属性具有非普通实现和自动方法，属性为只需值或变量的简单包装时。 若要显式声明的属性，使用`member`关键字。 此声明性语法后, 跟指定的语法`get`和`set`方法，也称为*访问器*。 在语法部分中所示的显式语法的各种形式用于读/写和只读的只写属性。 对于只读属性，只需定义`get`方法; 对于只写属性，定义仅`set`方法。 请注意，当属性同时具有`get`和`set`访问器中，替代语法，可指定特性和是不同的每个访问器，如下面的代码中所示的可访问性修饰符。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3201.fs)]

对于读/写属性，同时具有`get`和`set`方法、 的顺序`get`和`set`可逆转。 或者，你可以提供有关所示的语法`get`仅为所示的语法和`set`仅而不是使用组合的语法。 执行此操作，从而更便于注释掉单个`get`或`set`方法时，如果这是你可能需要执行操作。 以下代码演示了此除了使用组合的语法。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3203.fs)]

私有值属性的数据被称为该保留*后备存储*。 要让编译器自动创建的后备存储，可以使用关键字`member val`，省略自我标识符，然后提供用于初始化属性的表达式。 如果该属性是可变的包括`with get, set`。 例如，下面的类类型包括两个自动实现的属性。 `Property1` 是只读的同时初始化为到主构造函数，提供的自变量和`Property2`是初始化为空字符串可设置属性：

```fsharp
type MyClass(property1 : int) =
member val Property1 = property1
member val Property2 = "" with get, set
```

自动实现的属性是一种类型，初始化的一部分，因此它们必须包含在任何其他成员定义之前就像`let`绑定和`do`类型定义中的绑定。 请注意在初始化时和每次访问此属性时不只会计算初始化自动实现的属性的表达式。 此行为的行为是属性的相反的显式实现。 这实际上意味着，代码来初始化这些属性将添加到类的构造函数。 请考虑下面的代码显示此区别：

```fsharp
type MyClass() =
    let random  = new System.Random()
    member val AutoProperty = random.Next() with get, set
    member this.ExplicitProperty = random.Next()

let class1 = new MyClass()

printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.AutoProperty = %d" class1.AutoProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
printfn "class1.ExplicitProperty = %d" class1.ExplicitProperty
```

**输出**

```
class1.AutoProperty = 1853799794
class1.AutoProperty = 1853799794
class1.ExplicitProperty = 978922705
class1.ExplicitProperty = 1131210765
```

前面的代码的输出显示 AutoProperty 的值不变时重复调用而 ExplicitProperty 更改每次调用时。 此示例演示一个自动实现属性的表达式不会评估每个时间，是原样显式属性的 getter 方法。


>[!WARNING]
有某些库，如实体框架 (`System.Data.Entity`)，可以在不很好地使用自动实现属性的初始化的基类构造函数中执行自定义操作。 在这些情况下，请尝试使用显式的属性。

属性可以是类、 结构、 可区分的联合、 记录、 接口和类型扩展的成员，并且也可以在对象表达式中定义。

特性可以应用于属性。 将特性应用到的属性，请在单独的属性前面的行上写入属性。 有关更多信息，请参阅[特性](../attributes.md)。

默认情况下，属性是公共的。 可访问性修饰符也可以应用于属性。 若要应用可访问性修饰符，如果将其添加的属性名之前立即它旨在两者都适用`get`和`set`方法; 这些方法将其之前添加`get`和`set`是否可访问性不同的关键字所需的每个访问器。 *可访问性修饰符*可以是以下之一： `public`， `private`， `internal`。 有关详细信息，请参阅[访问控制](../access-control.md)。

每次访问属性时，都会执行属性实现。


## <a name="static-and-instance-properties"></a>静态和实例属性
属性可以是静态或实例属性。 静态属性可以调用实例情况下，和用于与不具有单个对象的类型相关联的值。 对于静态属性，省略自我标识符。 对于实例属性需要自我标识符。

以下的静态属性定义基于一个方案使用的静态字段`myStaticValue`，它是属性的后备存储。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3204.fs)]

属性也可以是数组一样，在这种情况下调用它们*索引属性*。 有关详细信息，请参阅[索引化属性](indexed-properties.md)。


## <a name="type-annotation-for-properties"></a>属性的类型批注
在许多情况下，编译器具有足够的信息来推断来自后备存储类型的属性的类型，但你可以通过添加类型批注中显式设置的类型。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3205.fs)]

## <a name="using-property-set-accessors"></a>使用属性 set 访问器
您可以设置提供的属性`set`通过使用访问器`<-`运算符。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3206.fs)]

输出**20**。


## <a name="abstract-properties"></a>抽象属性
属性可以是抽象的。 与方法一样，`abstract`只是与属性关联的虚拟调度意味着。 抽象属性可以是真正抽象的也就是说，没有同一类中定义。 因此，包含此属性的类是一个抽象类。 或者，抽象可能只是意味着属性是虚拟的且在这种情况下，定义必须存在于同一个类。 请注意，抽象属性不能为私有的并且一个访问器是抽象的其他必须也是抽象的。 有关抽象类的详细信息，请参阅[抽象类](../abstract-classes.md)。

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet3207.fs)]

## <a name="see-also"></a>请参阅
[成员](index.md)

[方法](methods.md)
