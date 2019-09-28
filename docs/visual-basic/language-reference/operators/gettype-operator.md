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
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592156"
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="378e2-102">GetType 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="378e2-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="378e2-103">为指定的类型返回 @no__t 0 对象。</span><span class="sxs-lookup"><span data-stu-id="378e2-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="378e2-104">@No__t 0 对象提供有关类型的信息，如其属性、方法和事件。</span><span class="sxs-lookup"><span data-stu-id="378e2-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="378e2-105">语法</span><span class="sxs-lookup"><span data-stu-id="378e2-105">Syntax</span></span>  
  
```vb  
GetType(typename)  
```  
  
## <a name="parameters"></a><span data-ttu-id="378e2-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="378e2-106">Parameters</span></span>  
  
|<span data-ttu-id="378e2-107">参数</span><span class="sxs-lookup"><span data-stu-id="378e2-107">Parameter</span></span>|<span data-ttu-id="378e2-108">描述</span><span class="sxs-lookup"><span data-stu-id="378e2-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="378e2-109">要获取其信息的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="378e2-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="378e2-110">备注</span><span class="sxs-lookup"><span data-stu-id="378e2-110">Remarks</span></span>  
 <span data-ttu-id="378e2-111">@No__t-0 运算符返回指定 `typename` 的 @no__t 的对象。</span><span class="sxs-lookup"><span data-stu-id="378e2-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="378e2-112">可以在 `typename` 中传递任何已定义类型的名称。</span><span class="sxs-lookup"><span data-stu-id="378e2-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="378e2-113">这包括：</span><span class="sxs-lookup"><span data-stu-id="378e2-113">This includes the following:</span></span>  
  
- <span data-ttu-id="378e2-114">任何 Visual Basic 数据类型，如 @no__t 或 @no__t。</span><span class="sxs-lookup"><span data-stu-id="378e2-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
- <span data-ttu-id="378e2-115">任何 .NET Framework 类、结构、模块或接口，如 @no__t 或 @no__t。</span><span class="sxs-lookup"><span data-stu-id="378e2-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="378e2-116">应用程序定义的任何类、结构、模块或接口。</span><span class="sxs-lookup"><span data-stu-id="378e2-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
- <span data-ttu-id="378e2-117">应用程序定义的任何数组。</span><span class="sxs-lookup"><span data-stu-id="378e2-117">Any array defined by your application.</span></span>  
  
- <span data-ttu-id="378e2-118">应用程序定义的任何委托。</span><span class="sxs-lookup"><span data-stu-id="378e2-118">Any delegate defined by your application.</span></span>  
  
- <span data-ttu-id="378e2-119">Visual Basic、.NET Framework 或应用程序定义的任何枚举。</span><span class="sxs-lookup"><span data-stu-id="378e2-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="378e2-120">如果要获取对象变量的类型对象，请使用 <xref:System.Type.GetType%2A?displayProperty=nameWithType> 方法。</span><span class="sxs-lookup"><span data-stu-id="378e2-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="378e2-121">在以下情况下，`GetType` 运算符可能很有用：</span><span class="sxs-lookup"><span data-stu-id="378e2-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
- <span data-ttu-id="378e2-122">您必须在运行时访问类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="378e2-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="378e2-123">@No__t 0 对象提供类型成员和部署信息等元数据。</span><span class="sxs-lookup"><span data-stu-id="378e2-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="378e2-124">例如，您需要这样做来反映程序集。</span><span class="sxs-lookup"><span data-stu-id="378e2-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="378e2-125">有关详细信息，请参阅 <xref:System.Reflection?displayProperty=nameWithType> 。</span><span class="sxs-lookup"><span data-stu-id="378e2-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
- <span data-ttu-id="378e2-126">要比较两个对象引用，以确定它们是否引用相同类型的实例。</span><span class="sxs-lookup"><span data-stu-id="378e2-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="378e2-127">如果是这样，则 `GetType` 返回对同一 @no__t 1 对象的引用。</span><span class="sxs-lookup"><span data-stu-id="378e2-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="378e2-128">示例</span><span class="sxs-lookup"><span data-stu-id="378e2-128">Example</span></span>  
 <span data-ttu-id="378e2-129">下面的示例显示了正在使用的 @no__t 0 运算符。</span><span class="sxs-lookup"><span data-stu-id="378e2-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#26)]  
  
## <a name="see-also"></a><span data-ttu-id="378e2-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="378e2-130">See also</span></span>

- [<span data-ttu-id="378e2-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="378e2-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="378e2-132">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="378e2-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="378e2-133">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="378e2-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
