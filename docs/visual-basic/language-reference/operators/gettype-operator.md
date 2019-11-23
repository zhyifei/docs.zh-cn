---
title: GetType 运算符 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
ms.openlocfilehash: 2e3e05973f2ef72fef5e429bc98cc58b4b21f2c2
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592156"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="07d1a-102">GetType 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="07d1a-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="07d1a-103">返回指定类型的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="07d1a-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="07d1a-104"><xref:System.Type> 对象提供有关类型的信息，如其属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="07d1a-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07d1a-105">语法</span><span class="sxs-lookup"><span data-stu-id="07d1a-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="07d1a-106">参数</span><span class="sxs-lookup"><span data-stu-id="07d1a-106">Parameters</span></span>  
  
|<span data-ttu-id="07d1a-107">参数</span><span class="sxs-lookup"><span data-stu-id="07d1a-107">Parameter</span></span>|<span data-ttu-id="07d1a-108">说明</span><span class="sxs-lookup"><span data-stu-id="07d1a-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="07d1a-109">要获取其信息的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="07d1a-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="07d1a-110">备注</span><span class="sxs-lookup"><span data-stu-id="07d1a-110">Remarks</span></span>  
 <span data-ttu-id="07d1a-111">`GetType` 运算符返回指定 `typename`的 <xref:System.Type> 对象。</span><span class="sxs-lookup"><span data-stu-id="07d1a-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="07d1a-112">可以在 `typename`中传递任何已定义类型的名称。</span><span class="sxs-lookup"><span data-stu-id="07d1a-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="07d1a-113">这包括：</span><span class="sxs-lookup"><span data-stu-id="07d1a-113">This includes the following:</span></span>  
  
- <span data-ttu-id="07d1a-114">任何 Visual Basic 数据类型，如 `Boolean` 或 `Date`。</span><span class="sxs-lookup"><span data-stu-id="07d1a-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="07d1a-115">任何 .NET Framework 类、结构、模块或接口，如 <xref:System.ArgumentException?displayProperty=nameWithType> 或 <xref:System.Double?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="07d1a-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="07d1a-116">应用程序定义的任何类、结构、模块或接口。</span><span class="sxs-lookup"><span data-stu-id="07d1a-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="07d1a-117">应用程序定义的任何数组。</span><span class="sxs-lookup"><span data-stu-id="07d1a-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="07d1a-118">应用程序定义的任何委托。</span><span class="sxs-lookup"><span data-stu-id="07d1a-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="07d1a-119">Visual Basic、.NET Framework 或应用程序定义的任何枚举。</span><span class="sxs-lookup"><span data-stu-id="07d1a-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="07d1a-120">如果要获取对象变量的类型对象，请使用 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="07d1a-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="07d1a-121">在以下情况下，`GetType` 运算符可能很有用：</span><span class="sxs-lookup"><span data-stu-id="07d1a-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="07d1a-122">您必须在运行时访问类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="07d1a-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="07d1a-123"><xref:System.Type> 对象提供了元数据，例如类型成员和部署信息。</span><span class="sxs-lookup"><span data-stu-id="07d1a-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="07d1a-124">例如，您需要这样做来反映程序集。</span><span class="sxs-lookup"><span data-stu-id="07d1a-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="07d1a-125">有关详细信息，请参阅 <xref:System.Reflection?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="07d1a-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="07d1a-126">要比较两个对象引用，以确定它们是否引用相同类型的实例。</span><span class="sxs-lookup"><span data-stu-id="07d1a-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="07d1a-127">如果是这样，`GetType` 将返回对同一 <xref:System.Type> 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="07d1a-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07d1a-128">示例</span><span class="sxs-lookup"><span data-stu-id="07d1a-128">Example</span></span>  
 <span data-ttu-id="07d1a-129">下面的示例演示了使用中的 `GetType` 运算符。</span><span class="sxs-lookup"><span data-stu-id="07d1a-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="07d1a-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="07d1a-130">See also</span></span>

- [<span data-ttu-id="07d1a-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="07d1a-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="07d1a-132">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="07d1a-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="07d1a-133">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="07d1a-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
