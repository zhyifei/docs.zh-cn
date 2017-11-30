---
title: "GetType 运算符 (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.GetType
helpviewer_keywords:
- GetType operator [Visual Basic]
- GetType keyword [Visual Basic]
ms.assetid: 4f733297-2503-4607-850c-15eba65fff90
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 38a984dce44133936f7f163e6afb20f0f336377c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="gettype-operator-visual-basic"></a><span data-ttu-id="86c42-102">GetType 运算符 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86c42-102">GetType Operator (Visual Basic)</span></span>
<span data-ttu-id="86c42-103">返回<xref:System.Type>指定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="86c42-103">Returns a <xref:System.Type> object for the specified type.</span></span> <span data-ttu-id="86c42-104"><xref:System.Type>对象提供了有关如其属性、 方法和事件类型的信息。</span><span class="sxs-lookup"><span data-stu-id="86c42-104">The <xref:System.Type> object provides information about the type such as its properties, methods, and events.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86c42-105">语法</span><span class="sxs-lookup"><span data-stu-id="86c42-105">Syntax</span></span>  
  
```  
GetType(typename)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86c42-106">参数</span><span class="sxs-lookup"><span data-stu-id="86c42-106">Parameters</span></span>  
  
|<span data-ttu-id="86c42-107">参数</span><span class="sxs-lookup"><span data-stu-id="86c42-107">Parameter</span></span>|<span data-ttu-id="86c42-108">描述</span><span class="sxs-lookup"><span data-stu-id="86c42-108">Description</span></span>|  
|---|---|  
|`typename`|<span data-ttu-id="86c42-109">为其所需信息的类型的名称。</span><span class="sxs-lookup"><span data-stu-id="86c42-109">The name of the type for which you desire information.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86c42-110">备注</span><span class="sxs-lookup"><span data-stu-id="86c42-110">Remarks</span></span>  
 <span data-ttu-id="86c42-111">`GetType`运算符返回<xref:System.Type>的指定对象的`typename`。</span><span class="sxs-lookup"><span data-stu-id="86c42-111">The `GetType` operator returns the <xref:System.Type> object for the specified `typename`.</span></span> <span data-ttu-id="86c42-112">可以将在任何定义的类型名称传递给`typename`。</span><span class="sxs-lookup"><span data-stu-id="86c42-112">You can pass the name of any defined type in `typename`.</span></span> <span data-ttu-id="86c42-113">这包括：</span><span class="sxs-lookup"><span data-stu-id="86c42-113">This includes the following:</span></span>  
  
-   <span data-ttu-id="86c42-114">任何 Visual Basic 数据类型，如`Boolean`或`Date`。</span><span class="sxs-lookup"><span data-stu-id="86c42-114">Any Visual Basic data type, such as `Boolean` or `Date`.</span></span>  
  
-   <span data-ttu-id="86c42-115">任何.NET Framework 类、 结构、 模块或接口，如<xref:System.ArgumentException?displayProperty=nameWithType>或<xref:System.Double?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="86c42-115">Any .NET Framework class, structure, module, or interface, such as <xref:System.ArgumentException?displayProperty=nameWithType> or <xref:System.Double?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="86c42-116">任何类、 结构、 模块或接口定义应用程序。</span><span class="sxs-lookup"><span data-stu-id="86c42-116">Any class, structure, module, or interface defined by your application.</span></span>  
  
-   <span data-ttu-id="86c42-117">应用程序定义的任何数组。</span><span class="sxs-lookup"><span data-stu-id="86c42-117">Any array defined by your application.</span></span>  
  
-   <span data-ttu-id="86c42-118">应用程序定义的任何委托。</span><span class="sxs-lookup"><span data-stu-id="86c42-118">Any delegate defined by your application.</span></span>  
  
-   <span data-ttu-id="86c42-119">任何由 Visual Basic、.NET Framework 中或你的应用程序定义的枚举。</span><span class="sxs-lookup"><span data-stu-id="86c42-119">Any enumeration defined by Visual Basic, the .NET Framework, or your application.</span></span>  
  
 <span data-ttu-id="86c42-120">如果你想要获取的对象变量的类型对象，使用<xref:System.Type.GetType%2A?displayProperty=nameWithType>方法。</span><span class="sxs-lookup"><span data-stu-id="86c42-120">If you want to get the type object of an object variable, use the <xref:System.Type.GetType%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="86c42-121">`GetType`运算符可以在以下情况下有用：</span><span class="sxs-lookup"><span data-stu-id="86c42-121">The `GetType` operator can be useful in the following circumstances:</span></span>  
  
-   <span data-ttu-id="86c42-122">必须在运行时访问类型的元数据。</span><span class="sxs-lookup"><span data-stu-id="86c42-122">You must access the metadata for a type at run time.</span></span> <span data-ttu-id="86c42-123"><xref:System.Type>对象提供元数据，例如类型成员和部署信息。</span><span class="sxs-lookup"><span data-stu-id="86c42-123">The <xref:System.Type> object supplies metadata such as type members and deployment information.</span></span> <span data-ttu-id="86c42-124">您需要它，例如，在程序集上进行反射。</span><span class="sxs-lookup"><span data-stu-id="86c42-124">You need this, for example, to reflect over an assembly.</span></span> <span data-ttu-id="86c42-125">有关详细信息，请参阅<xref:System.Reflection?displayProperty=nameWithType>。</span><span class="sxs-lookup"><span data-stu-id="86c42-125">For more information, see <xref:System.Reflection?displayProperty=nameWithType>.</span></span>  
  
-   <span data-ttu-id="86c42-126">你想要比较两个对象引用，以了解它们是否引用相同类型的实例。</span><span class="sxs-lookup"><span data-stu-id="86c42-126">You want to compare two object references to see if they refer to instances of the same type.</span></span> <span data-ttu-id="86c42-127">如果他们这样做，`GetType`返回对相同的引用<xref:System.Type>对象。</span><span class="sxs-lookup"><span data-stu-id="86c42-127">If they do, `GetType` returns references to the same <xref:System.Type> object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86c42-128">示例</span><span class="sxs-lookup"><span data-stu-id="86c42-128">Example</span></span>  
 <span data-ttu-id="86c42-129">下面的示例演示`GetType`中使用的运算符。</span><span class="sxs-lookup"><span data-stu-id="86c42-129">The following examples show the `GetType` operator in use.</span></span>  
  
 [!code-vb[VbVbalrOperators#26](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/gettype-operator_1.vb)]  
  
## <a name="see-also"></a><span data-ttu-id="86c42-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86c42-130">See Also</span></span>  
 [<span data-ttu-id="86c42-131">Visual Basic 中的运算符优先级</span><span class="sxs-lookup"><span data-stu-id="86c42-131">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)  
 [<span data-ttu-id="86c42-132">按功能列出的运算符</span><span class="sxs-lookup"><span data-stu-id="86c42-132">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)  
 [<span data-ttu-id="86c42-133">运算符和表达式</span><span class="sxs-lookup"><span data-stu-id="86c42-133">Operators and Expressions</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/index.md)
