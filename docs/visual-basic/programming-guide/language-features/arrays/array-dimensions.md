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
ms.openlocfilehash: 0b4e7c9e253f94e1e28700c8669d28799ab69d91
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "62053712"
---
# <a name="array-dimensions-in-visual-basic"></a><span data-ttu-id="dfa32-102">Array Dimensions in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="dfa32-102">Array Dimensions in Visual Basic</span></span>
<span data-ttu-id="dfa32-103">一个*维度*是在其中您可以更改数组的元素的规范的方向。</span><span class="sxs-lookup"><span data-stu-id="dfa32-103">A *dimension* is a direction in which you can vary the specification of an array's elements.</span></span> <span data-ttu-id="dfa32-104">一个数组，其中保存总销量，月份中的每一天有一个维度 （每月天数）。</span><span class="sxs-lookup"><span data-stu-id="dfa32-104">An array that holds the sales total for each day of the month has one dimension (the day of the month).</span></span> <span data-ttu-id="dfa32-105">保存总销量由部门的月份中的每一天的数组具有两个维度 （部门编号和每月天数）。</span><span class="sxs-lookup"><span data-stu-id="dfa32-105">An array that holds the sales total by department for each day of the month has two dimensions (the department number and the day of the month).</span></span> <span data-ttu-id="dfa32-106">名为的维数的数组具有其*排名*。</span><span class="sxs-lookup"><span data-stu-id="dfa32-106">The number of dimensions an array has is called its *rank*.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfa32-107">可以使用<xref:System.Array.Rank%2A>属性来确定多少维数的数组具有。</span><span class="sxs-lookup"><span data-stu-id="dfa32-107">You can use the <xref:System.Array.Rank%2A> property to determine the how many dimensions an array has.</span></span>  
  
## <a name="working-with-dimensions"></a><span data-ttu-id="dfa32-108">使用的维度</span><span class="sxs-lookup"><span data-stu-id="dfa32-108">Working with Dimensions</span></span>  
 <span data-ttu-id="dfa32-109">通过提供指定数组的元素*索引*或*下标*为每个维度。</span><span class="sxs-lookup"><span data-stu-id="dfa32-109">You specify an element of an array by supplying an *index* or *subscript* for each of its dimensions.</span></span> <span data-ttu-id="dfa32-110">元素是从 0 到最高的索引，该维度连续沿每个维度。</span><span class="sxs-lookup"><span data-stu-id="dfa32-110">The elements are contiguous along each dimension from index 0 through the highest index for that dimension.</span></span>  
  
 <span data-ttu-id="dfa32-111">下图显示具有不同秩的数组的概念结构。</span><span class="sxs-lookup"><span data-stu-id="dfa32-111">The following illustrations show the conceptual structure of arrays with different ranks.</span></span> <span data-ttu-id="dfa32-112">在图例中的每个元素显示对其进行访问的索引值。</span><span class="sxs-lookup"><span data-stu-id="dfa32-112">Each element in the illustrations shows the index values that access it.</span></span> <span data-ttu-id="dfa32-113">例如，可以通过指定索引访问的二维数组的第二个行的第一个元素`(1, 0)`。</span><span class="sxs-lookup"><span data-stu-id="dfa32-113">For example, you can access the first element of the second row of the two-dimensional array by specifying indexes `(1, 0)`.</span></span>  
  
 ![图，显示一个一维数组。](./media/array-dimensions/one-dimensional-array.gif)  
  
 ![图，显示一个二维数组。](./media/array-dimensions/two-dimensional-array.gif)  
  
 ![图，显示三维数组。](./media/array-dimensions/three-dimensional-array.gif)  
  
### <a name="one-dimension"></a><span data-ttu-id="dfa32-117">一个维度</span><span class="sxs-lookup"><span data-stu-id="dfa32-117">One Dimension</span></span>  
 <span data-ttu-id="dfa32-118">多个数组具有只有一个维度，例如每个年龄的用户数。</span><span class="sxs-lookup"><span data-stu-id="dfa32-118">Many arrays have only one dimension, such as the number of people of each age.</span></span> <span data-ttu-id="dfa32-119">若要指定的元素的唯一要求是该元素为其保留计数的年龄。</span><span class="sxs-lookup"><span data-stu-id="dfa32-119">The only requirement to specify an element is the age for which that element holds the count.</span></span> <span data-ttu-id="dfa32-120">因此，此类数组使用只有一个索引。</span><span class="sxs-lookup"><span data-stu-id="dfa32-120">Therefore, such an array uses only one index.</span></span> <span data-ttu-id="dfa32-121">下面的示例声明一个变量来保存*的一维数组*于阶段 0 到 120 计数的年龄。</span><span class="sxs-lookup"><span data-stu-id="dfa32-121">The following example declares a variable to hold a *one-dimensional array* of age counts for ages 0 through 120.</span></span>  
  
```  
Dim ageCounts(120) As UInteger  
```  
  
### <a name="two-dimensions"></a><span data-ttu-id="dfa32-122">两个维度</span><span class="sxs-lookup"><span data-stu-id="dfa32-122">Two Dimensions</span></span>  
 <span data-ttu-id="dfa32-123">某些数组具有两个维度，如在校园上每个生成的每个楼层机构数量。</span><span class="sxs-lookup"><span data-stu-id="dfa32-123">Some arrays have two dimensions, such as the number of offices on each floor of each building on a campus.</span></span> <span data-ttu-id="dfa32-124">元素的规范要求的建筑号和基底，并且每个元素均包含构造和层的组合的计数。</span><span class="sxs-lookup"><span data-stu-id="dfa32-124">The specification of an element requires both the building number and the floor, and each element holds the count for that combination of building and floor.</span></span> <span data-ttu-id="dfa32-125">因此，此类数组使用两个索引。</span><span class="sxs-lookup"><span data-stu-id="dfa32-125">Therefore, such an array uses two indexes.</span></span> <span data-ttu-id="dfa32-126">下面的示例声明一个变量来保存*二维数组*office 计数，0 到 40 建筑和楼层从 0 到 5。</span><span class="sxs-lookup"><span data-stu-id="dfa32-126">The following example declares a variable to hold a *two-dimensional array* of office counts, for buildings 0 through 40 and floors 0 through 5.</span></span>  
  
```  
Dim officeCounts(40, 5) As Byte  
```  
  
 <span data-ttu-id="dfa32-127">二维数组也称为*矩形数组*。</span><span class="sxs-lookup"><span data-stu-id="dfa32-127">A two-dimensional array is also called a *rectangular array*.</span></span>  
  
### <a name="three-dimensions"></a><span data-ttu-id="dfa32-128">三个维度</span><span class="sxs-lookup"><span data-stu-id="dfa32-128">Three Dimensions</span></span>  
 <span data-ttu-id="dfa32-129">几个数组具有三个维度，如三维空间中的值。</span><span class="sxs-lookup"><span data-stu-id="dfa32-129">A few arrays have three dimensions, such as values in three-dimensional space.</span></span> <span data-ttu-id="dfa32-130">一个数组，此类使用三个索引，在这种情况下表示 x、 y 和 z 坐标的物理空间。</span><span class="sxs-lookup"><span data-stu-id="dfa32-130">Such an array uses three indexes, which in this case represent the x, y, and z coordinates of physical space.</span></span> <span data-ttu-id="dfa32-131">下面的示例声明一个变量来保存*三维数组*的气温三维卷中的不同位置。</span><span class="sxs-lookup"><span data-stu-id="dfa32-131">The following example declares a variable to hold a *three-dimensional array* of air temperatures at various points in a three-dimensional volume.</span></span>  
  
```  
Dim airTemperatures(99, 99, 24) As Single  
```  
  
### <a name="more-than-three-dimensions"></a><span data-ttu-id="dfa32-132">超过三个维度</span><span class="sxs-lookup"><span data-stu-id="dfa32-132">More than Three Dimensions</span></span>  
 <span data-ttu-id="dfa32-133">虽然数组可以有多达 32 维数，很少会有三个。</span><span class="sxs-lookup"><span data-stu-id="dfa32-133">Although an array can have as many as 32 dimensions, it is rare to have more than three.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfa32-134">当将维度添加到一个数组时，数组所需的总存储会急剧增大，因此谨慎使用多维数组。</span><span class="sxs-lookup"><span data-stu-id="dfa32-134">When you add dimensions to an array, the total storage needed by the array increases considerably, so use multidimensional arrays with care.</span></span>  
  
## <a name="using-different-dimensions"></a><span data-ttu-id="dfa32-135">使用不同的维度</span><span class="sxs-lookup"><span data-stu-id="dfa32-135">Using Different Dimensions</span></span>  
 <span data-ttu-id="dfa32-136">假设您想要跟踪的每一天的存在月销售额。</span><span class="sxs-lookup"><span data-stu-id="dfa32-136">Suppose you want to track sales amounts for every day of the present month.</span></span> <span data-ttu-id="dfa32-137">可能会声明 31 元素的一维数组，一个用于每一天的月份，如下面的示例显示了。</span><span class="sxs-lookup"><span data-stu-id="dfa32-137">You might declare a one-dimensional array with 31 elements, one for each day of the month, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(30) As Double  
```  
  
 <span data-ttu-id="dfa32-138">现在假设你想要跟踪不仅对每一天的每个月，但还为一年中的每个月的相同信息。</span><span class="sxs-lookup"><span data-stu-id="dfa32-138">Now suppose you want to track the same information not only for every day of a month but also for every month of the year.</span></span> <span data-ttu-id="dfa32-139">如以下示例所示，可能会声明一个二维数组具有 12 行 （适用于几个月） 和 （对于天），31 列。</span><span class="sxs-lookup"><span data-stu-id="dfa32-139">You might declare a two-dimensional array with 12 rows (for the months) and 31 columns (for the days), as the following example shows.</span></span>  
  
```  
Dim salesAmounts(11, 30) As Double  
```  
  
 <span data-ttu-id="dfa32-140">现在假设你决定让你的数组将保存多个为一年的信息。</span><span class="sxs-lookup"><span data-stu-id="dfa32-140">Now suppose you decide to have your array hold information for more than one year.</span></span> <span data-ttu-id="dfa32-141">如果你想要跟踪的 5 年的销售额，您可能如以下示例所示声明具有 5 层、 12 行和 31 列的三维数组。</span><span class="sxs-lookup"><span data-stu-id="dfa32-141">If you want to track sales amounts for 5 years, you could declare a three-dimensional array with 5 layers, 12 rows, and 31 columns, as the following example shows.</span></span>  
  
```  
Dim salesAmounts(4, 11, 30) As Double  
```  
  
 <span data-ttu-id="dfa32-142">注意，因为每个索引值从 0 到变化其最大值，每个维度的`salesAmounts`该维度被声明为一个小于所需的长度。</span><span class="sxs-lookup"><span data-stu-id="dfa32-142">Note that, because each index varies from 0 to its maximum, each dimension of `salesAmounts` is declared as one less than the required length for that dimension.</span></span> <span data-ttu-id="dfa32-143">另请注意，数组的大小会增加与每个新的维度。</span><span class="sxs-lookup"><span data-stu-id="dfa32-143">Note also that the size of the array increases with each new dimension.</span></span> <span data-ttu-id="dfa32-144">在上述示例中的三个大小分别为 31、 372 和 1860 个元素。</span><span class="sxs-lookup"><span data-stu-id="dfa32-144">The three sizes in the preceding examples are 31, 372, and 1,860 elements respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dfa32-145">您可以创建一个数组，而无需使用`Dim`语句或`New`子句。</span><span class="sxs-lookup"><span data-stu-id="dfa32-145">You can create an array without using the `Dim` statement or the `New` clause.</span></span> <span data-ttu-id="dfa32-146">例如，可以调用<xref:System.Array.CreateInstance%2A>方法或另一个组件可以通过你的代码以这种方式创建的数组。</span><span class="sxs-lookup"><span data-stu-id="dfa32-146">For example, you can call the <xref:System.Array.CreateInstance%2A> method, or another component can pass your code an array created in this manner.</span></span> <span data-ttu-id="dfa32-147">此类数组可以有 0 以外的下限。</span><span class="sxs-lookup"><span data-stu-id="dfa32-147">Such an array can have a lower bound other than 0.</span></span> <span data-ttu-id="dfa32-148">始终可以通过使用测试维度的下限<xref:System.Array.GetLowerBound%2A>方法或`LBound`函数。</span><span class="sxs-lookup"><span data-stu-id="dfa32-148">You can always test for the lower bound of a dimension by using the <xref:System.Array.GetLowerBound%2A> method or the `LBound` function.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dfa32-149">请参阅</span><span class="sxs-lookup"><span data-stu-id="dfa32-149">See also</span></span>

- [<span data-ttu-id="dfa32-150">数组</span><span class="sxs-lookup"><span data-stu-id="dfa32-150">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="dfa32-151">数组疑难解答</span><span class="sxs-lookup"><span data-stu-id="dfa32-151">Troubleshooting Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)
