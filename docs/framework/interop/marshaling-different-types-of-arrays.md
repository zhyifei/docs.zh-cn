---
title: "封送处理不同类型的数组"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- marshaling, Arrays sample
- data marshaling, Arrays sample
ms.assetid: c5ac9920-5b6e-4dc9-bf2d-1f6f8ad3b0bf
caps.latest.revision: 15
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3a91c74cf6734776fd6356c201e6754f34a8fbcf
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="marshaling-different-types-of-arrays"></a><span data-ttu-id="8d0e0-102">封送处理不同类型的数组</span><span class="sxs-lookup"><span data-stu-id="8d0e0-102">Marshaling Different Types of Arrays</span></span>
<span data-ttu-id="8d0e0-103">数组是包含有一个或多个相同类型的元素的托管代码中的引用类型。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-103">An array is a reference type in managed code that contains one or more elements of the same type.</span></span> <span data-ttu-id="8d0e0-104">尽管数组是引用类型，但它们却作为 In 参数传递到非托管函数。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-104">Although arrays are reference types, they are passed as In parameters to unmanaged functions.</span></span> <span data-ttu-id="8d0e0-105">此行为与托管数组传递到托管对象的方式不一致，数组作为 In/Out 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-105">This behavior is inconsistent with way managed arrays are passed to managed objects, which is as In/Out parameters.</span></span> <span data-ttu-id="8d0e0-106">有关其他详细信息，请参阅 [复制和锁定](../../../docs/framework/interop/copying-and-pinning.md)。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-106">For additional details, see [Copying and Pinning](../../../docs/framework/interop/copying-and-pinning.md).</span></span>  
  
 <span data-ttu-id="8d0e0-107">下表列出了数组的封送处理选项，并描述了它们的用法。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-107">The following table lists marshaling options for arrays and describes their usage.</span></span>  
  
|<span data-ttu-id="8d0e0-108">数组</span><span class="sxs-lookup"><span data-stu-id="8d0e0-108">Array</span></span>|<span data-ttu-id="8d0e0-109">描述</span><span class="sxs-lookup"><span data-stu-id="8d0e0-109">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="8d0e0-110">通过值传递的整数。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-110">Of integers by value.</span></span>|<span data-ttu-id="8d0e0-111">将整数的数组作为 In 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-111">Passes an array of integers as an In parameter.</span></span>|  
|<span data-ttu-id="8d0e0-112">通过引用传递的整数。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-112">Of integers by reference.</span></span>|<span data-ttu-id="8d0e0-113">将整数的数组作为 In/Out 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-113">Passes an array of integers as an In/Out parameter.</span></span>|  
|<span data-ttu-id="8d0e0-114">通过值传递的整数（二维）。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-114">Of integers by value (two-dimensional).</span></span>|<span data-ttu-id="8d0e0-115">将整数的矩阵作为 In 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-115">Passes a matrix of integers as an In parameter.</span></span>|  
|<span data-ttu-id="8d0e0-116">通过值传递的字符串。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-116">Of strings by value.</span></span>|<span data-ttu-id="8d0e0-117">将字符串的数组作为 In 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-117">Passes an array of strings as an In parameter.</span></span>|  
|<span data-ttu-id="8d0e0-118">传递具有整数的结构。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-118">Of structures with integers.</span></span>|<span data-ttu-id="8d0e0-119">将包含整数的结构数组作为 In 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-119">Passes an array of structures that contain integers as an In parameter.</span></span>|  
|<span data-ttu-id="8d0e0-120">传递具有字符串的结构。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-120">Of structures with strings.</span></span>|<span data-ttu-id="8d0e0-121">将仅包含整数的结构数组作为 In/Out 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-121">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="8d0e0-122">可以更改数组的成员。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-122">Members of the array can be changed.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="8d0e0-123">示例</span><span class="sxs-lookup"><span data-stu-id="8d0e0-123">Example</span></span>  
 <span data-ttu-id="8d0e0-124">本示例演示如何传递以下类型的数组：</span><span class="sxs-lookup"><span data-stu-id="8d0e0-124">This sample demonstrates how to pass the following types of arrays:</span></span>  
  
-   <span data-ttu-id="8d0e0-125">通过值传递的整数数组。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-125">Array of integers by value.</span></span>  
  
-   <span data-ttu-id="8d0e0-126">通过引用传递的整数数组（可以调整大小）。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-126">Array of integers by reference, which can be resized.</span></span>  
  
-   <span data-ttu-id="8d0e0-127">通过值传递的整数多维数组（矩阵）。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-127">Multidimensional array (matrix) of integers by value.</span></span>  
  
-   <span data-ttu-id="8d0e0-128">通过值传递的字符串数组。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-128">Array of strings by value.</span></span>  
  
-   <span data-ttu-id="8d0e0-129">传递具有整数的结构数组。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-129">Array of structures with integers.</span></span>  
  
-   <span data-ttu-id="8d0e0-130">传递具有字符串的结构数组。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-130">Array of structures with strings.</span></span>  
  
 <span data-ttu-id="8d0e0-131">除非数组由引用显式地进行封送处理，否则将以默认行为将数组封送为 In 参数。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-131">Unless an array is explicitly marshaled by reference, the default behavior marshals the array as an In parameter.</span></span> <span data-ttu-id="8d0e0-132">通过显示应用 <xref:System.Runtime.InteropServices.InAttribute> 和 <xref:System.Runtime.InteropServices.OutAttribute> 属性，可以更改此行为。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-132">You can change this behavior by applying the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes explicitly.</span></span>  
  
 <span data-ttu-id="8d0e0-133">数组示例使用以下非托管函数，这些函数与其原始函数声明一起显示：</span><span class="sxs-lookup"><span data-stu-id="8d0e0-133">The Arrays sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="8d0e0-134">从 PinvokeLib.dll 导出的**TestArrayOfInts** 。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-134">**TestArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfInts(int* pArray, int pSize);  
    ```  
  
-   <span data-ttu-id="8d0e0-135">从 PinvokeLib.dll 导出的**TestRefArrayOfInts** 。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-135">**TestRefArrayOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestRefArrayOfInts(int** ppArray, int* pSize);  
    ```  
  
-   <span data-ttu-id="8d0e0-136">从 PinvokeLib.dll 导出的**TestMatrixOfInts** 。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-136">**TestMatrixOfInts** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestMatrixOfInts(int pMatrix[][COL_DIM], int row);  
    ```  
  
-   <span data-ttu-id="8d0e0-137">从 PinvokeLib.dll 导出的**TestArrayOfStrings** 。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-137">**TestArrayOfStrings** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStrings(char** ppStrArray, int size);  
    ```  
  
-   <span data-ttu-id="8d0e0-138">从 PinvokeLib.dll 导出的**TestArrayOfStructs** 。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-138">**TestArrayOfStructs** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs(MYPOINT* pPointArray, int size);  
    ```  
  
-   <span data-ttu-id="8d0e0-139">从 PinvokeLib.dll 导出的**TestArrayOfStructs2** 。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-139">**TestArrayOfStructs2** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestArrayOfStructs2 (MYPERSON* pPersonArray, int size);  
    ```  
  
 <span data-ttu-id="8d0e0-140">[PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) 是一个自定义的非托管库，它包含之前列出的函数、两个结构变量（ **MYPOINT** 和 **MYPERSON**）的实现。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-140">[PinvokeLib.dll](http://msdn.microsoft.com/en-us/5d1438d7-9946-489d-8ede-6c694a08f614) is a custom unmanaged library that contains implementations for the previously listed functions and two structure variables, **MYPOINT** and **MYPERSON**.</span></span> <span data-ttu-id="8d0e0-141">此结构包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="8d0e0-141">The structures contain the following elements:</span></span>  
  
```  
typedef struct _MYPOINT  
{  
   int x;   
   int y;   
} MYPOINT;  
  
typedef struct _MYPERSON  
{  
   char* first;   
   char* last;   
} MYPERSON;  
```  
  
 <span data-ttu-id="8d0e0-142">在此示例中， `MyPoint` 和 `MyPerson` 结构包含嵌入类型。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-142">In this sample, the `MyPoint` and `MyPerson` structures contain embedded types.</span></span> <span data-ttu-id="8d0e0-143">设置 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 特性，以确保成员在内存中按照它们出现的顺序进行排列。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-143">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="8d0e0-144">`LibWrap` 类包含一组 `App` 类调用的方法。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-144">The `LibWrap` class contains a set of methods called by the `App` class.</span></span> <span data-ttu-id="8d0e0-145">有关传递数组的特定详细信息，请参阅以下示例中的注释。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-145">For specific details about passing arrays, see the comments in the following sample.</span></span> <span data-ttu-id="8d0e0-146">默认情况下，一个引用类型的数组将作为 In 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-146">An array, which is a reference type, is passed as an In parameter by default.</span></span> <span data-ttu-id="8d0e0-147">为使调用方接收结果， **InAttribute** 和 **OutAttribute** 必须显式应用于包含该数组的参数。</span><span class="sxs-lookup"><span data-stu-id="8d0e0-147">For the caller to receive the results, **InAttribute** and **OutAttribute** must be applied explicitly to the argument containing the array.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="8d0e0-148">声明原型</span><span class="sxs-lookup"><span data-stu-id="8d0e0-148">Declaring Prototypes</span></span>  
 <span data-ttu-id="8d0e0-149">[!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)] [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]</span><span class="sxs-lookup"><span data-stu-id="8d0e0-149">[!code-csharp[Conceptual.Interop.Marshaling#31](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#31)] [!code-vb[Conceptual.Interop.Marshaling#31](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#31)]</span></span>  
  
### <a name="calling-functions"></a><span data-ttu-id="8d0e0-150">调用函数</span><span class="sxs-lookup"><span data-stu-id="8d0e0-150">Calling Functions</span></span>  
 <span data-ttu-id="8d0e0-151">[!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)] [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]</span><span class="sxs-lookup"><span data-stu-id="8d0e0-151">[!code-csharp[Conceptual.Interop.Marshaling#32](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/arrays.cs#32)] [!code-vb[Conceptual.Interop.Marshaling#32](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/arrays.vb#32)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d0e0-152">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8d0e0-152">See Also</span></span>  
 <span data-ttu-id="8d0e0-153">[封送类型数组](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8) </span><span class="sxs-lookup"><span data-stu-id="8d0e0-153">[Marshaling Arrays of Types](http://msdn.microsoft.com/en-us/049b1c1b-228f-4445-88ec-91bc7fd4b1e8) </span></span>  
 <span data-ttu-id="8d0e0-154">[平台调用数据类型](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f) </span><span class="sxs-lookup"><span data-stu-id="8d0e0-154">[Platform Invoke Data Types](http://msdn.microsoft.com/en-us/16014d9f-d6bd-481e-83f0-df11377c550f) </span></span>  
 [<span data-ttu-id="8d0e0-155">在托管代码中创建原型</span><span class="sxs-lookup"><span data-stu-id="8d0e0-155">Creating Prototypes in Managed Code</span></span>](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)

