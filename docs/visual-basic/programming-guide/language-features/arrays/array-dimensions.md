---
title: Array Dimensions in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- dimensions, arrays
- arrays [Visual Basic], dimensions
- arrays [Visual Basic], rectangular
- arrays [Visual Basic], rank
- rectangular arrays
- ranking, arrays
ms.assetid: 385e911b-18c1-4e98-9924-c6d279101dd9
ms.openlocfilehash: cf295288dd034d744dceb71b5c58278be5cc2a2f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33651751"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="d74e3-102">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d74e3-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="d74e3-103">A*维度*是在其中您可以改变数组的元素的规范方向。</span><span class="sxs-lookup"><span data-stu-id="d74e3-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="d74e3-104">保存总销量，每月的每一天的数组具有一个维度 （每月天数）。</span><span class="sxs-lookup"><span data-stu-id="d74e3-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="d74e3-105">保存总销量由部门的每一天的月份的数组具有两个维度 （部门数和每月天数）。</span><span class="sxs-lookup"><span data-stu-id="d74e3-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="d74e3-106">调用的维数的数组具有其*级别*。</span><span class="sxs-lookup"><span data-stu-id="d74e3-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d74e3-107">你可以使用<xref:System.Array.Rank%2A>属性来确定多少维数的数组具有。</span><span class="sxs-lookup"><span data-stu-id="d74e3-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="d74e3-108">使用的维度</span><span class="sxs-lookup"><span data-stu-id="d74e3-108">Working with Dimensions</span></span>  
 <span data-ttu-id="d74e3-109">通过提供指定数组的数组元素*索引*或*下标*其维度的每个。</span><span class="sxs-lookup"><span data-stu-id="d74e3-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="d74e3-110">元素将从 0 到最高的索引，该维度连续沿每个维度。</span><span class="sxs-lookup"><span data-stu-id="d74e3-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="d74e3-111">下图显示具有不同的秩的数组的概念结构。</span><span class="sxs-lookup"><span data-stu-id="d74e3-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="d74e3-112">每个元素的插图内显示访问它的索引值。</span><span class="sxs-lookup"><span data-stu-id="d74e3-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="d74e3-113">例如，可以通过指定索引访问二维数组的第二行的第一个元素`(1, 0)`。</span><span class="sxs-lookup"><span data-stu-id="d74e3-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 <span data-ttu-id="d74e3-114">![一个示意图&#45;维数组](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span><span class="sxs-lookup"><span data-stu-id="d74e3-114">![Graphic diagram of one&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimone.gif "ArrayExDimOne")</span></span>  
<span data-ttu-id="d74e3-115">一维数组</span><span class="sxs-lookup"><span data-stu-id="d74e3-115">One-dimensional array</span></span>  
  
 <span data-ttu-id="d74e3-116">![两个图形关系图&#45;维数组](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span><span class="sxs-lookup"><span data-stu-id="d74e3-116">![Graphic diagram of two&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimtwo.gif "ArrayExDimTwo")</span></span>  
<span data-ttu-id="d74e3-117">二维数组</span><span class="sxs-lookup"><span data-stu-id="d74e3-117">Two-dimensional array</span></span>  
  
 <span data-ttu-id="d74e3-118">![三个示意图&#45;维数组](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span><span class="sxs-lookup"><span data-stu-id="d74e3-118">![Graphic diagram of three&#45;dimensional array](../../../../visual-basic/programming-guide/language-features/arrays/media/arrayexdimthree.gif "ArrayExDimThree")</span></span>  
<span data-ttu-id="d74e3-119">三维数组</span><span class="sxs-lookup"><span data-stu-id="d74e3-119">Three-dimensional array</span></span>  
  
### <a name="one-dimension"></a><span data-ttu-id="d74e3-120">一个维度</span><span class="sxs-lookup"><span data-stu-id="d74e3-120">One Dimension</span></span>  
 <span data-ttu-id="d74e3-121">多个数组具有只有一个维度，如每个期限的人员数。</span><span class="sxs-lookup"><span data-stu-id="d74e3-121">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="d74e3-122">要指定某个元素的唯一要求是，该元素包含计数的期限。</span><span class="sxs-lookup"><span data-stu-id="d74e3-122">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="d74e3-123">因此，这样的数组使用只有一个索引。</span><span class="sxs-lookup"><span data-stu-id="d74e3-123">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="d74e3-124">下面的示例声明一个变量以保存*一维数组*的年龄 0 到 120 计数的年龄。</span><span class="sxs-lookup"><span data-stu-id="d74e3-124">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="d74e3-125">两个维度</span><span class="sxs-lookup"><span data-stu-id="d74e3-125">Two Dimensions</span></span>  
 <span data-ttu-id="d74e3-126">某些数组具有两个维度，如在上一区域每个生成的每一层上的机构数量。</span><span class="sxs-lookup"><span data-stu-id="d74e3-126">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="d74e3-127">元素的规范要求的建筑号和基底，和每个元素包含构造和层的该组合的计数。</span><span class="sxs-lookup"><span data-stu-id="d74e3-127">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="d74e3-128">因此，这样的数组使用这两个索引。</span><span class="sxs-lookup"><span data-stu-id="d74e3-128">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="d74e3-129">下面的示例声明一个变量以保存*二维数组*office 计数，建筑物从 0 到 40 和楼层从 0 到 5。</span><span class="sxs-lookup"><span data-stu-id="d74e3-129">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="d74e3-130">二维数组也被称为*矩形数组*。</span><span class="sxs-lookup"><span data-stu-id="d74e3-130">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="d74e3-131">三个维度</span><span class="sxs-lookup"><span data-stu-id="d74e3-131">Three Dimensions</span></span>  
 <span data-ttu-id="d74e3-132">几个数组具有三个维度，如在三维空间中的值。</span><span class="sxs-lookup"><span data-stu-id="d74e3-132">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="d74e3-133">这样的数组使用三个索引，在这种情况下表示 x、 y 和 z 坐标的物理空间。</span><span class="sxs-lookup"><span data-stu-id="d74e3-133">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="d74e3-134">下面的示例声明一个变量以保存*三维数组*的气温三维卷中的各个点。</span><span class="sxs-lookup"><span data-stu-id="d74e3-134">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="d74e3-135">三个以上的维度</span><span class="sxs-lookup"><span data-stu-id="d74e3-135">More than Three Dimensions</span></span>  
 <span data-ttu-id="d74e3-136">尽管数组可具有多达 32 维度，但很少使用多个三种。</span><span class="sxs-lookup"><span data-stu-id="d74e3-136">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d74e3-137">将维度添加到一个数组，数组所需的总存储增加有相当大，因此使用多维数组时要小心。</span><span class="sxs-lookup"><span data-stu-id="d74e3-137">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="d74e3-138">使用不同维度</span><span class="sxs-lookup"><span data-stu-id="d74e3-138">Using Different Dimensions</span></span>  
 <span data-ttu-id="d74e3-139">假设你想要跟踪的存在月中每天的销售额。</span><span class="sxs-lookup"><span data-stu-id="d74e3-139">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="d74e3-140">一个用于每个月的日期，如下面的示例演示，你可能会声明 31 元素的一维数组。</span><span class="sxs-lookup"><span data-stu-id="d74e3-140">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="d74e3-141">现在假设你想要跟踪的相同信息不仅每天每月的而且还要为每个月的年份。</span><span class="sxs-lookup"><span data-stu-id="d74e3-141">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="d74e3-142">如以下示例所示，可能会声明一个二维数组具有 12 行 （表示月为单位） 和 （对于天），31 列。</span><span class="sxs-lookup"><span data-stu-id="d74e3-142">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="d74e3-143">现在假设你决定让你的阵列将保存多个为一年的信息。</span><span class="sxs-lookup"><span data-stu-id="d74e3-143">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="d74e3-144">如果你想要跟踪的 5 年的销售额，你无法声明具有 5 层、 12 行和 31 列的三维数组，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="d74e3-144">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="d74e3-145">请注意，由于每个索引会发生从 0 到其最大值，每个维度的变化`salesAmounts`该维度被声明为一个小于所需的长度。</span><span class="sxs-lookup"><span data-stu-id="d74e3-145">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="d74e3-146">另请注意，数组的大小会增加随每个新的维度。</span><span class="sxs-lookup"><span data-stu-id="d74e3-146">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="d74e3-147">前面的示例中的三个大小分别为 31、 372 和 1860 个元素。</span><span class="sxs-lookup"><span data-stu-id="d74e3-147">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d74e3-148">你可以创建一个数组，而不使用`Dim`语句或`New`子句。</span><span class="sxs-lookup"><span data-stu-id="d74e3-148">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="d74e3-149">例如，你可以调用<xref:System.Array.CreateInstance%2A>方法或另一个组件可以通过你的代码以这种方式创建的数组。</span><span class="sxs-lookup"><span data-stu-id="d74e3-149">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="d74e3-150">这样的数组可以下限为非 0。</span><span class="sxs-lookup"><span data-stu-id="d74e3-150">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="d74e3-151">始终可以通过使用测试维度的下限<xref:System.Array.GetLowerBound%2A>方法或`LBound`函数。</span><span class="sxs-lookup"><span data-stu-id="d74e3-151">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d74e3-152">请参阅</span><span class="sxs-lookup"><span data-stu-id="d74e3-152">See Also</span></span>  
 [<span data-ttu-id="d74e3-153">数组</span><span class="sxs-lookup"><span data-stu-id="d74e3-153">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [<span data-ttu-id="d74e3-154">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="d74e3-154">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
