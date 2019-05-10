---
title: GetType 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 3366a0d1a90667cf1d9b58b211892ad264849c59
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64633232"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="00d01-102">GetType 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="00d01-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="00d01-103">返回<xref:System.Type>指定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="00d01-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="00d01-104"><xref:System.Type>对象提供有关其属性、 方法和事件等类型的信息。</span><span class="sxs-lookup"><span data-stu-id="00d01-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00d01-105">语法</span><span class="sxs-lookup"><span data-stu-id="00d01-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="00d01-106">参数</span><span class="sxs-lookup"><span data-stu-id="00d01-106">Parameters</span></span>  
  
|<span data-ttu-id="00d01-107">参数</span><span class="sxs-lookup"><span data-stu-id="00d01-107">Parameter</span></span>|<span data-ttu-id="00d01-108">描述</span><span class="sxs-lookup"><span data-stu-id="00d01-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="00d01-109">为其所需的信息类型的名称。</span><span class="sxs-lookup"><span data-stu-id="00d01-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00d01-110">备注</span><span class="sxs-lookup"><span data-stu-id="00d01-110">Remarks</span></span>  
 <span data-ttu-id="00d01-111">`GetType`运算符将返回<xref:System.Type>的指定对象的`typename`。</span><span class="sxs-lookup"><span data-stu-id="00d01-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="00d01-112">可以在任何已定义类型的名称将传递`typename`。</span><span class="sxs-lookup"><span data-stu-id="00d01-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="00d01-113">这包括：</span><span class="sxs-lookup"><span data-stu-id="00d01-113">This includes the following:</span></span>  
  
- <span data-ttu-id="00d01-114">任何 Visual Basic 数据类型，如`Boolean`或`Date`。</span><span class="sxs-lookup"><span data-stu-id="00d01-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="00d01-115">任何.NET Framework 类、 结构、 模块或接口，如<xref:System.ArgumentException?displayProperty=nameWithType>或<xref:System.Double?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="00d01-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="00d01-116">任何类、 结构、 模块或接口定义的应用程序。</span><span class="sxs-lookup"><span data-stu-id="00d01-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="00d01-117">任何由你的应用程序定义的数组。</span><span class="sxs-lookup"><span data-stu-id="00d01-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="00d01-118">任何由你的应用程序定义的委托。</span><span class="sxs-lookup"><span data-stu-id="00d01-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="00d01-119">任何由 Visual Basic、.NET Framework 中或你的应用程序定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="00d01-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="00d01-120">如果你想要获取的对象变量的类型对象，使用<xref:System.Type.GetType%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="00d01-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="00d01-121">`GetType`运算符只能在以下情况下有用：</span><span class="sxs-lookup"><span data-stu-id="00d01-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="00d01-122">必须在运行时访问类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="00d01-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="00d01-123"><xref:System.Type>对象提供元数据，例如类型成员和部署信息。</span><span class="sxs-lookup"><span data-stu-id="00d01-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="00d01-124">您需要它，例如，在程序集上进行反射。</span><span class="sxs-lookup"><span data-stu-id="00d01-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="00d01-125">有关详细信息，请参阅 <xref:System.Reflection?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="00d01-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="00d01-126">你想要比较两个对象引用引用相同类型的实例。</span><span class="sxs-lookup"><span data-stu-id="00d01-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="00d01-127">如果是这样，`GetType`返回对相同的引用<xref:System.Type>对象。</span><span class="sxs-lookup"><span data-stu-id="00d01-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="00d01-128">示例</span><span class="sxs-lookup"><span data-stu-id="00d01-128">Example</span></span>  
 <span data-ttu-id="00d01-129">下面的示例演示`GetType`中使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="00d01-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="00d01-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="00d01-130">See also</span></span>

- [<span data-ttu-id="00d01-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="00d01-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="00d01-132">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="00d01-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="00d01-133">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="00d01-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
