---
title: Visual Basic 中属性和变量的差异
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- variables [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- variables [Visual Basic], definition
- Visual Basic code, variables
- Visual Basic code, properties
- properties [Visual Basic], values
- properties [Visual Basic], defined
- variables [Visual Basic], and properties
- properties [Visual Basic], and variables
ms.assetid: 7a03a8be-5381-431f-bd7c-16e887e4e07b
ms.openlocfilehash: f2388f091278d398b5e8f3b82f147ab69937f2aa
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54689518"
---
# <a name="differences-between-properties-and-variables-in-visual-basic"></a><span data-ttu-id="6006d-102">Visual Basic 中属性和变量的差异</span><span class="sxs-lookup"><span data-stu-id="6006d-102">Differences Between Properties and Variables in Visual Basic</span></span>
<span data-ttu-id="6006d-103">变量和属性都表示可以访问的值。</span><span class="sxs-lookup"><span data-stu-id="6006d-103">Variables and properties both represent values that you can access.</span></span> <span data-ttu-id="6006d-104">但是，有存储和实现之间的差异。</span><span class="sxs-lookup"><span data-stu-id="6006d-104">However, there are differences in storage and implementation.</span></span>  
  
## <a name="variables"></a><span data-ttu-id="6006d-105">变量</span><span class="sxs-lookup"><span data-stu-id="6006d-105">Variables</span></span>  
 <span data-ttu-id="6006d-106">一个*变量*直接对应于内存位置。</span><span class="sxs-lookup"><span data-stu-id="6006d-106">A *variable* corresponds directly to a memory location.</span></span> <span data-ttu-id="6006d-107">定义具有单个声明语句的变量。</span><span class="sxs-lookup"><span data-stu-id="6006d-107">You define a variable with a single declaration statement.</span></span> <span data-ttu-id="6006d-108">变量可以是*局部变量*，定义在过程内，可仅在该过程中，也可以是*成员变量*，而不是在任何中模块、 类或结构定义过程。</span><span class="sxs-lookup"><span data-stu-id="6006d-108">A variable can be a *local variable*, defined inside a procedure and available only within that procedure, or it can be a *member variable*, defined in a module, class, or structure but not inside any procedure.</span></span> <span data-ttu-id="6006d-109">成员变量也称为*字段*。</span><span class="sxs-lookup"><span data-stu-id="6006d-109">A member variable is also called a *field*.</span></span>  
  
## <a name="properties"></a><span data-ttu-id="6006d-110">Properties</span><span class="sxs-lookup"><span data-stu-id="6006d-110">Properties</span></span>  
 <span data-ttu-id="6006d-111">一个*属性*是模块、 类或结构上定义的数据元素。</span><span class="sxs-lookup"><span data-stu-id="6006d-111">A *property* is a data element defined on a module, class, or structure.</span></span> <span data-ttu-id="6006d-112">定义属性的代码块之间`Property`和`End Property`语句。</span><span class="sxs-lookup"><span data-stu-id="6006d-112">You define a property with a code block between the `Property` and `End Property` statements.</span></span> <span data-ttu-id="6006d-113">代码块包含`Get`过程中，`Set`过程中，或两者。</span><span class="sxs-lookup"><span data-stu-id="6006d-113">The code block contains a `Get` procedure, a `Set` procedure, or both.</span></span> <span data-ttu-id="6006d-114">这些过程称为*属性过程*或*属性访问器*。</span><span class="sxs-lookup"><span data-stu-id="6006d-114">These procedures are called *property procedures* or *property accessors*.</span></span> <span data-ttu-id="6006d-115">除了检索或存储属性的值，它们还可以执行自定义操作，例如对访问计数器的更新。</span><span class="sxs-lookup"><span data-stu-id="6006d-115">In addition to retrieving or storing the property's value, they can also perform custom actions, such as updating an access counter.</span></span>  
  
## <a name="differences"></a><span data-ttu-id="6006d-116">差异</span><span class="sxs-lookup"><span data-stu-id="6006d-116">Differences</span></span>  
 <span data-ttu-id="6006d-117">下表显示了变量和属性之间的一些重要差异。</span><span class="sxs-lookup"><span data-stu-id="6006d-117">The following table shows some important differences between variables and properties.</span></span>  
  
|<span data-ttu-id="6006d-118">差异点</span><span class="sxs-lookup"><span data-stu-id="6006d-118">Point of difference</span></span>|<span data-ttu-id="6006d-119">变量</span><span class="sxs-lookup"><span data-stu-id="6006d-119">Variable</span></span>|<span data-ttu-id="6006d-120">属性</span><span class="sxs-lookup"><span data-stu-id="6006d-120">Property</span></span>|  
|-------------------------|--------------|--------------|  
|<span data-ttu-id="6006d-121">声明</span><span class="sxs-lookup"><span data-stu-id="6006d-121">Declaration</span></span>|<span data-ttu-id="6006d-122">单个声明语句</span><span class="sxs-lookup"><span data-stu-id="6006d-122">Single declaration statement</span></span>|<span data-ttu-id="6006d-123">系列中的代码块的语句</span><span class="sxs-lookup"><span data-stu-id="6006d-123">Series of statements in a code block</span></span>|  
|<span data-ttu-id="6006d-124">实现</span><span class="sxs-lookup"><span data-stu-id="6006d-124">Implementation</span></span>|<span data-ttu-id="6006d-125">单个存储位置</span><span class="sxs-lookup"><span data-stu-id="6006d-125">Single storage location</span></span>|<span data-ttu-id="6006d-126">可执行代码 （属性过程）</span><span class="sxs-lookup"><span data-stu-id="6006d-126">Executable code (property procedures)</span></span>|  
|<span data-ttu-id="6006d-127">存储</span><span class="sxs-lookup"><span data-stu-id="6006d-127">Storage</span></span>|<span data-ttu-id="6006d-128">直接与变量的值相关联</span><span class="sxs-lookup"><span data-stu-id="6006d-128">Directly associated with variable's value</span></span>|<span data-ttu-id="6006d-129">通常具有内部存储之外的属性包含类或模块不可用</span><span class="sxs-lookup"><span data-stu-id="6006d-129">Typically has internal storage not available outside the property's containing class or module</span></span><br /><br /> <span data-ttu-id="6006d-130">属性的值可能会或可能不作为存储的元素存在<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6006d-130">Property's value might or might not exist as a stored element <sup>1</sup></span></span>|  
|<span data-ttu-id="6006d-131">可执行代码</span><span class="sxs-lookup"><span data-stu-id="6006d-131">Executable code</span></span>|<span data-ttu-id="6006d-132">无</span><span class="sxs-lookup"><span data-stu-id="6006d-132">None</span></span>|<span data-ttu-id="6006d-133">必须具有至少一个过程</span><span class="sxs-lookup"><span data-stu-id="6006d-133">Must have at least one procedure</span></span>|  
|<span data-ttu-id="6006d-134">读取和写入访问权限</span><span class="sxs-lookup"><span data-stu-id="6006d-134">Read and write access</span></span>|<span data-ttu-id="6006d-135">读/写或只读的</span><span class="sxs-lookup"><span data-stu-id="6006d-135">Read/write or read-only</span></span>|<span data-ttu-id="6006d-136">读/写、 只读的或只写</span><span class="sxs-lookup"><span data-stu-id="6006d-136">Read/write, read-only, or write-only</span></span>|  
|<span data-ttu-id="6006d-137">自定义操作 （除了接受或返回值）</span><span class="sxs-lookup"><span data-stu-id="6006d-137">Custom actions (in addition to accepting or returning value)</span></span>|<span data-ttu-id="6006d-138">不可能</span><span class="sxs-lookup"><span data-stu-id="6006d-138">Not possible</span></span>|<span data-ttu-id="6006d-139">可以执行设置或检索属性值的一部分</span><span class="sxs-lookup"><span data-stu-id="6006d-139">Can be performed as part of setting or retrieving property value</span></span>|  
  
 <span data-ttu-id="6006d-140"><sup>1</sup>和变量，不同的属性值可能不直接对应于存储的单个项。</span><span class="sxs-lookup"><span data-stu-id="6006d-140"><sup>1</sup> Unlike a variable, the value of a property might not correspond directly to a single item of storage.</span></span> <span data-ttu-id="6006d-141">存储可能会拆分成方便或安全性，部分或的值可能会以加密形式存储。</span><span class="sxs-lookup"><span data-stu-id="6006d-141">The storage might be split into pieces for convenience or security, or the value might be stored in an encrypted form.</span></span> <span data-ttu-id="6006d-142">在这些情况下`Get`过程将汇编这些块或解密存储的值和`Set`过程会加密新值或将其拆分为构成的存储。</span><span class="sxs-lookup"><span data-stu-id="6006d-142">In these cases the `Get` procedure would assemble the pieces or decrypt the stored value, and the `Set` procedure would encrypt the new value or split it into the constituent storage.</span></span> <span data-ttu-id="6006d-143">属性值可以是临时的如一天时间，在这种情况下`Get`过程会计算得出其值动态每次访问的属性。</span><span class="sxs-lookup"><span data-stu-id="6006d-143">A property value might be ephemeral, like time of day, in which case the `Get` procedure would calculate it on the fly each time you access the property.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6006d-144">请参阅</span><span class="sxs-lookup"><span data-stu-id="6006d-144">See also</span></span>
- [<span data-ttu-id="6006d-145">属性过程</span><span class="sxs-lookup"><span data-stu-id="6006d-145">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="6006d-146">过程参数和自变量</span><span class="sxs-lookup"><span data-stu-id="6006d-146">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="6006d-147">Property 语句</span><span class="sxs-lookup"><span data-stu-id="6006d-147">Property Statement</span></span>](../../../../visual-basic/language-reference/statements/property-statement.md)
- [<span data-ttu-id="6006d-148">Dim 语句</span><span class="sxs-lookup"><span data-stu-id="6006d-148">Dim Statement</span></span>](../../../../visual-basic/language-reference/statements/dim-statement.md)
- [<span data-ttu-id="6006d-149">如何：创建属性</span><span class="sxs-lookup"><span data-stu-id="6006d-149">How to: Create a Property</span></span>](./how-to-create-a-property.md)
- [<span data-ttu-id="6006d-150">如何：声明具有混合的访问级别的属性</span><span class="sxs-lookup"><span data-stu-id="6006d-150">How to: Declare a Property with Mixed Access Levels</span></span>](./how-to-declare-a-property-with-mixed-access-levels.md)
- [<span data-ttu-id="6006d-151">如何：调用 Property 过程</span><span class="sxs-lookup"><span data-stu-id="6006d-151">How to: Call a Property Procedure</span></span>](./how-to-call-a-property-procedure.md)
- [<span data-ttu-id="6006d-152">如何：声明并在 Visual Basic 中调用默认属性</span><span class="sxs-lookup"><span data-stu-id="6006d-152">How to: Declare and Call a Default Property in Visual Basic</span></span>](./how-to-declare-and-call-a-default-property.md)
- [<span data-ttu-id="6006d-153">如何：在属性中放置值</span><span class="sxs-lookup"><span data-stu-id="6006d-153">How to: Put a Value in a Property</span></span>](./how-to-put-a-value-in-a-property.md)
- [<span data-ttu-id="6006d-154">如何：从属性获取一个值</span><span class="sxs-lookup"><span data-stu-id="6006d-154">How to: Get a Value from a Property</span></span>](./how-to-get-a-value-from-a-property.md)
