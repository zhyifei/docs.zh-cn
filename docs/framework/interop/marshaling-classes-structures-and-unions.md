---
title: 封送类、结构和联合
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- data marshaling, classes
- marshaling, unions
- marshaling, structures
- marshaling, samples
- data marshaling, structures
- platform invoke, marshaling data
- marshaling, classes
- data marshaling, unions
- data marshaling, samples
- data marshaling, platform invoke
- marshaling, platform invoke
ms.assetid: 027832a2-9b43-4fd9-9b45-7f4196261a4e
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: cc7141bb8fce5d5e1c2420a48d6081fa89aa0d53
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="marshaling-classes-structures-and-unions"></a><span data-ttu-id="89653-102">封送类、结构和联合</span><span class="sxs-lookup"><span data-stu-id="89653-102">Marshaling Classes, Structures, and Unions</span></span>
<span data-ttu-id="89653-103">.NET Framework 中类和结构非常相似。</span><span class="sxs-lookup"><span data-stu-id="89653-103">Classes and structures are similar in the .NET Framework.</span></span> <span data-ttu-id="89653-104">它们都可以具有字段、属性和事件。</span><span class="sxs-lookup"><span data-stu-id="89653-104">Both can have fields, properties, and events.</span></span> <span data-ttu-id="89653-105">并且都可以具有静态和非静态方法。</span><span class="sxs-lookup"><span data-stu-id="89653-105">They can also have static and nonstatic methods.</span></span> <span data-ttu-id="89653-106">一个显著区别是结构是值类型，而类是引用类型。</span><span class="sxs-lookup"><span data-stu-id="89653-106">One notable difference is that structures are value types and classes are reference types.</span></span>  
  
 <span data-ttu-id="89653-107">下表列出了类、结构和联合的封送处理选项；描述了它们的用法；并提供了到相应平台调用示例的链接。</span><span class="sxs-lookup"><span data-stu-id="89653-107">The following table lists marshaling options for classes, structures, and unions; describes their usage; and provides a link to the corresponding platform invoke sample.</span></span>  
  
|<span data-ttu-id="89653-108">类型</span><span class="sxs-lookup"><span data-stu-id="89653-108">Type</span></span>|<span data-ttu-id="89653-109">描述</span><span class="sxs-lookup"><span data-stu-id="89653-109">Description</span></span>|<span data-ttu-id="89653-110">示例</span><span class="sxs-lookup"><span data-stu-id="89653-110">Sample</span></span>|  
|----------|-----------------|------------|  
|<span data-ttu-id="89653-111">按值显示类。</span><span class="sxs-lookup"><span data-stu-id="89653-111">Class by value.</span></span>|<span data-ttu-id="89653-112">将具有整数成员的类传递为 In/Out 参数，与托管的情形相似。</span><span class="sxs-lookup"><span data-stu-id="89653-112">Passes a class with integer members as an In/Out parameter, like the managed case.</span></span>|<span data-ttu-id="89653-113">SysTime 示例</span><span class="sxs-lookup"><span data-stu-id="89653-113">SysTime sample</span></span>|  
|<span data-ttu-id="89653-114">按值显示结构。</span><span class="sxs-lookup"><span data-stu-id="89653-114">Structure by value.</span></span>|<span data-ttu-id="89653-115">将结构作为 In 参数传递。</span><span class="sxs-lookup"><span data-stu-id="89653-115">Passes structures as In parameters.</span></span>|<span data-ttu-id="89653-116">“结构”示例</span><span class="sxs-lookup"><span data-stu-id="89653-116">Structures sample</span></span>|  
|<span data-ttu-id="89653-117">按引用显示结构。</span><span class="sxs-lookup"><span data-stu-id="89653-117">Structure by reference.</span></span>|<span data-ttu-id="89653-118">将结构作为 In/Out 参数传递。</span><span class="sxs-lookup"><span data-stu-id="89653-118">Passes structures as In/Out parameters.</span></span>|<span data-ttu-id="89653-119">OSInfo 示例</span><span class="sxs-lookup"><span data-stu-id="89653-119">OSInfo sample</span></span>|  
|<span data-ttu-id="89653-120">具有内嵌结构（平展）的结构。</span><span class="sxs-lookup"><span data-stu-id="89653-120">Structure with nested structures (flattened).</span></span>|<span data-ttu-id="89653-121">传递非托管函数中表示内嵌结构的结构的类。</span><span class="sxs-lookup"><span data-stu-id="89653-121">Passes a class that represents a structure with nested structures in the unmanaged function.</span></span> <span data-ttu-id="89653-122">此结构在托管的原型中将平展为一个大的结构。</span><span class="sxs-lookup"><span data-stu-id="89653-122">The structure is flattened to one big structure in the managed prototype.</span></span>|<span data-ttu-id="89653-123">FindFile 示例</span><span class="sxs-lookup"><span data-stu-id="89653-123">FindFile sample</span></span>|  
|<span data-ttu-id="89653-124">具有指向另一结构的指针的结构。</span><span class="sxs-lookup"><span data-stu-id="89653-124">Structure with a pointer to another structure.</span></span>|<span data-ttu-id="89653-125">将包含指向第二结构的指针的结构作为成员传递。</span><span class="sxs-lookup"><span data-stu-id="89653-125">Passes a structure that contains a pointer to a second structure as a member.</span></span>|<span data-ttu-id="89653-126">结构示例</span><span class="sxs-lookup"><span data-stu-id="89653-126">Structures Sample</span></span>|  
|<span data-ttu-id="89653-127">按值显示具有整数的结构数组。</span><span class="sxs-lookup"><span data-stu-id="89653-127">Array of structures with integers by value.</span></span>|<span data-ttu-id="89653-128">将仅包含整数的结构数组作为 In/Out 参数进行传递。</span><span class="sxs-lookup"><span data-stu-id="89653-128">Passes an array of structures that contain only integers as an In/Out parameter.</span></span> <span data-ttu-id="89653-129">可以更改数组的成员。</span><span class="sxs-lookup"><span data-stu-id="89653-129">Members of the array can be changed.</span></span>|<span data-ttu-id="89653-130">“数组”示例</span><span class="sxs-lookup"><span data-stu-id="89653-130">Arrays Sample</span></span>|  
|<span data-ttu-id="89653-131">按引用显示具有整数和字符串的结构数组。</span><span class="sxs-lookup"><span data-stu-id="89653-131">Array of structures with integers and strings by reference.</span></span>|<span data-ttu-id="89653-132">将包含整数和字符串的结构数组作为 Out 参数传递。</span><span class="sxs-lookup"><span data-stu-id="89653-132">Passes an array of structures that contain integers and strings as an Out parameter.</span></span> <span data-ttu-id="89653-133">被调用的函数为数组分配内存。</span><span class="sxs-lookup"><span data-stu-id="89653-133">The called function allocates memory for the array.</span></span>|<span data-ttu-id="89653-134">OutArrayOfStructs 示例</span><span class="sxs-lookup"><span data-stu-id="89653-134">OutArrayOfStructs Sample</span></span>|  
|<span data-ttu-id="89653-135">具有值类型的联合。</span><span class="sxs-lookup"><span data-stu-id="89653-135">Unions with value types.</span></span>|<span data-ttu-id="89653-136">传递具有值类型（整数和双精度）的联合。</span><span class="sxs-lookup"><span data-stu-id="89653-136">Passes unions with value types (integer and double).</span></span>|<span data-ttu-id="89653-137">“联合”示例</span><span class="sxs-lookup"><span data-stu-id="89653-137">Unions sample</span></span>|  
|<span data-ttu-id="89653-138">具有混合类型的联合。</span><span class="sxs-lookup"><span data-stu-id="89653-138">Unions with mixed types.</span></span>|<span data-ttu-id="89653-139">传递具有混合类型（整数和字符串）的联合。</span><span class="sxs-lookup"><span data-stu-id="89653-139">Passes unions with mixed types (integer and string).</span></span>|<span data-ttu-id="89653-140">“联合”示例</span><span class="sxs-lookup"><span data-stu-id="89653-140">Unions sample</span></span>|  
|<span data-ttu-id="89653-141">结构中的 null 值。</span><span class="sxs-lookup"><span data-stu-id="89653-141">Null values in structure.</span></span>|<span data-ttu-id="89653-142">传递空引用（Visual Basic 中为 Nothing），而不传递对值类型的引用。</span><span class="sxs-lookup"><span data-stu-id="89653-142">Passes a null reference (**Nothing** in Visual Basic) instead of a reference to a value type.</span></span>|<span data-ttu-id="89653-143">HandleRef 示例</span><span class="sxs-lookup"><span data-stu-id="89653-143">HandleRef sample</span></span>|  
  
## <a name="structures-sample"></a><span data-ttu-id="89653-144">结构示例</span><span class="sxs-lookup"><span data-stu-id="89653-144">Structures sample</span></span>  
 <span data-ttu-id="89653-145">此示例演示了如何传递指向第二结构的结构、具有嵌入结构的结构和具有嵌入数组的结构。</span><span class="sxs-lookup"><span data-stu-id="89653-145">This sample demonstrates how to pass a structure that points to a second structure, pass a structure with an embedded structure, and pass a structure with an embedded array.</span></span>  
  
 <span data-ttu-id="89653-146">“结构”示例使用以下非托管函数（与原始函数声明一同显示）：</span><span class="sxs-lookup"><span data-stu-id="89653-146">The Structs sample uses the following unmanaged functions, shown with their original function declaration:</span></span>  
  
-   <span data-ttu-id="89653-147">从 PinvokeLib.dll 导出的 TestStructInStruct。</span><span class="sxs-lookup"><span data-stu-id="89653-147">**TestStructInStruct** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    int TestStructInStruct(MYPERSON2* pPerson2);  
    ```  
  
-   <span data-ttu-id="89653-148">从 PinvokeLib.dll 导出的 TestStructInStruct3。</span><span class="sxs-lookup"><span data-stu-id="89653-148">**TestStructInStruct3** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestStructInStruct3(MYPERSON3 person3);  
    ```  
  
-   <span data-ttu-id="89653-149">从 PinvokeLib.dll 导出的 TestArrayInStruct。</span><span class="sxs-lookup"><span data-stu-id="89653-149">**TestArrayInStruct** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestArrayInStruct( MYARRAYSTRUCT* pStruct );  
    ```  
  
 <span data-ttu-id="89653-150">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) 是一种自定义的非托管库，包含上述函数和 4 种结构（MYPERSON、MYPERSON2、MYPERSON3 和 MYARRAYSTRUCT）的实现。</span><span class="sxs-lookup"><span data-stu-id="89653-150">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) is a custom unmanaged library that contains implementations for the previously listed functions and four structures: **MYPERSON**, **MYPERSON2**, **MYPERSON3**, and **MYARRAYSTRUCT**.</span></span> <span data-ttu-id="89653-151">这些结构包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="89653-151">These structures contain the following elements:</span></span>  
  
```  
typedef struct _MYPERSON  
{  
   char* first;   
   char* last;   
} MYPERSON, *LP_MYPERSON;  
  
typedef struct _MYPERSON2  
{  
   MYPERSON* person;  
   int age;   
} MYPERSON2, *LP_MYPERSON2;  
  
typedef struct _MYPERSON3  
{  
   MYPERSON person;  
   int age;   
} MYPERSON3;  
  
typedef struct _MYARRAYSTRUCT  
{  
   bool flag;  
   int vals[ 3 ];   
} MYARRAYSTRUCT;  
```  
  
 <span data-ttu-id="89653-152">托管的 `MyPerson`、`MyPerson2`、`MyPerson3` 和 `MyArrayStruct` 结构具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="89653-152">The managed `MyPerson`, `MyPerson2`, `MyPerson3`, and `MyArrayStruct` structures have the following characteristic:</span></span>  
  
-   <span data-ttu-id="89653-153">`MyPerson` 仅包含字符串成员。</span><span class="sxs-lookup"><span data-stu-id="89653-153">`MyPerson` contains only string members.</span></span> <span data-ttu-id="89653-154">[CharSet](specifying-a-character-set.md) 字段在传递到非托管函数时将字符串设置为 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="89653-154">The [CharSet](specifying-a-character-set.md) field sets the strings to ANSI format when passed to the unmanaged function.</span></span>  
  
-   <span data-ttu-id="89653-155">`MyPerson2` 将 IntPtr 包含到 `MyPerson` 结构中。</span><span class="sxs-lookup"><span data-stu-id="89653-155">`MyPerson2` contains an **IntPtr** to the `MyPerson` structure.</span></span> <span data-ttu-id="89653-156">IntPtr 类型替换指向非托管结构的原始指针，因为 .NET Framework 应用程序不使用指针，除非代码被标记为“不安全”。</span><span class="sxs-lookup"><span data-stu-id="89653-156">The **IntPtr** type replaces the original pointer to the unmanaged structure because .NET Framework applications do not use pointers unless the code is marked **unsafe**.</span></span>  
  
-   <span data-ttu-id="89653-157">`MyPerson3` 将 `MyPerson` 作为嵌入结构包含在内。</span><span class="sxs-lookup"><span data-stu-id="89653-157">`MyPerson3` contains `MyPerson` as an embedded structure.</span></span> <span data-ttu-id="89653-158">嵌入其他结构的结构可通过将嵌入结构的元素直接放入主结构中来进行平展，还可以保留为嵌入结构，如本示例中操作所示。</span><span class="sxs-lookup"><span data-stu-id="89653-158">A structure embedded within another structure can be flattened by placing the elements of the embedded structure directly into the main structure, or it can be left as an embedded structure, as is done in this sample.</span></span>  
  
-   <span data-ttu-id="89653-159">`MyArrayStruct` 包含整数数组。</span><span class="sxs-lookup"><span data-stu-id="89653-159">`MyArrayStruct` contains an array of integers.</span></span> <span data-ttu-id="89653-160"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性将 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举值设置为 ByValArray，此值用于指示数组中的元素数。</span><span class="sxs-lookup"><span data-stu-id="89653-160">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration value to **ByValArray**, which is used to indicate the number of elements in the array.</span></span>  
  
 <span data-ttu-id="89653-161">对于此示例中的所有结构，应用 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性以确保成员在内存中按出现的顺序进行排列。</span><span class="sxs-lookup"><span data-stu-id="89653-161">For all structures in this sample, the <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is applied to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="89653-162">`LibWrap` 类包含 `App` 类所调用的 `TestStructInStruct`、`TestStructInStruct3` 和 `TestArrayInStruct` 方法的托管原型。</span><span class="sxs-lookup"><span data-stu-id="89653-162">The `LibWrap` class contains managed prototypes for the `TestStructInStruct`, `TestStructInStruct3`, and `TestArrayInStruct` methods called by the `App` class.</span></span> <span data-ttu-id="89653-163">每个原型均声明一个参数，如下所示：</span><span class="sxs-lookup"><span data-stu-id="89653-163">Each prototype declares a single parameter, as follows:</span></span>  
  
-   <span data-ttu-id="89653-164">`TestStructInStruct` 将对 `MyPerson2` 类型的引用声明为其参数。</span><span class="sxs-lookup"><span data-stu-id="89653-164">`TestStructInStruct` declares a reference to type `MyPerson2` as its parameter.</span></span>  
  
-   <span data-ttu-id="89653-165">`TestStructInStruct3` 将 `MyPerson3` 类型声明为其参数并按值传递此参数。</span><span class="sxs-lookup"><span data-stu-id="89653-165">`TestStructInStruct3` declares type `MyPerson3` as its parameter and passes the parameter by value.</span></span>  
  
-   <span data-ttu-id="89653-166">`TestArrayInStruct` 将对 `MyArrayStruct` 类型的引用声明为其参数。</span><span class="sxs-lookup"><span data-stu-id="89653-166">`TestArrayInStruct` declares a reference to type `MyArrayStruct` as its parameter.</span></span>  
  
 <span data-ttu-id="89653-167">作为方法自变量的结构按值传递，除非此参数包含 ref（Visual Basic 中为 ByRef）关键字。</span><span class="sxs-lookup"><span data-stu-id="89653-167">Structures as arguments to methods are passed by value unless the parameter contains the **ref** (**ByRef** in Visual Basic) keyword.</span></span> <span data-ttu-id="89653-168">例如，`TestStructInStruct` 方法将对 `MyPerson2` 类型对象的引用（地址的值）传递到非托管代码。</span><span class="sxs-lookup"><span data-stu-id="89653-168">For example, the `TestStructInStruct` method passes a reference (the value of an address) to an object of type `MyPerson2` to unmanaged code.</span></span> <span data-ttu-id="89653-169">为了处理 `MyPerson2` 指向的结构，此示例创建了具有指定大小的缓冲区，并同时使用 <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> 和 <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> 方法返回其地址。</span><span class="sxs-lookup"><span data-stu-id="89653-169">To manipulate the structure that `MyPerson2` points to, the sample creates a buffer of a specified size and returns its address by combining the <xref:System.Runtime.InteropServices.Marshal.AllocCoTaskMem%2A?displayProperty=nameWithType> and <xref:System.Runtime.InteropServices.Marshal.SizeOf%2A?displayProperty=nameWithType> methods.</span></span> <span data-ttu-id="89653-170">然后，此示例将该托管结构的内容复制到非托管的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="89653-170">Next, the sample copies the content of the managed structure to the unmanaged buffer.</span></span> <span data-ttu-id="89653-171">最后，此示例使用 <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> 方法将非托管缓冲区的数据封送到托管对象，并使用 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> 方法释放非托管的内存块。</span><span class="sxs-lookup"><span data-stu-id="89653-171">Finally, the sample uses the <xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A?displayProperty=nameWithType> method to marshal data from the unmanaged buffer to a managed object and the <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A?displayProperty=nameWithType> method to free the unmanaged block of memory.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="89653-172">声明原型</span><span class="sxs-lookup"><span data-stu-id="89653-172">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#23)]
 [!code-csharp[Conceptual.Interop.Marshaling#23](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#23)]
 [!code-vb[Conceptual.Interop.Marshaling#23](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#23)]  
  
### <a name="calling-functions"></a><span data-ttu-id="89653-173">调用函数</span><span class="sxs-lookup"><span data-stu-id="89653-173">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/structures.cpp#24)]
 [!code-csharp[Conceptual.Interop.Marshaling#24](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/structures.cs#24)]
 [!code-vb[Conceptual.Interop.Marshaling#24](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/structures.vb#24)]  
  
## <a name="findfile-sample"></a><span data-ttu-id="89653-174">FindFile 示例</span><span class="sxs-lookup"><span data-stu-id="89653-174">FindFile sample</span></span>  
 <span data-ttu-id="89653-175">此示例演示了如何将包含第二、嵌入结构的结构传递到非托管函数。</span><span class="sxs-lookup"><span data-stu-id="89653-175">This sample demonstrates how to pass a structure that contains a second, embedded structure to an unmanaged function.</span></span> <span data-ttu-id="89653-176">它还演示了如何使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性在结构中声明固定长度的数组。</span><span class="sxs-lookup"><span data-stu-id="89653-176">It also demonstrates how to use the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to declare a fixed-length array within the structure.</span></span> <span data-ttu-id="89653-177">在此示例中，嵌入的结构元素将添加到父结构。</span><span class="sxs-lookup"><span data-stu-id="89653-177">In this sample, the embedded structure elements are added to the parent structure.</span></span> <span data-ttu-id="89653-178">有关未平展的嵌入结构的示例，请参阅[结构示例](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="89653-178">For a sample of an embedded structure that is not flattened, see [Structures Sample](https://msdn.microsoft.com/library/96a62265-dcf9-4608-bc0a-1f762ab9f48e(v=vs.100)).</span></span>  
  
 <span data-ttu-id="89653-179">FindFile 示例使用以下的非托管函数（与其原始函数声明一同显示）：</span><span class="sxs-lookup"><span data-stu-id="89653-179">The FindFile sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="89653-180">从 Kernel32.dll 导出的 FindFirstFile。</span><span class="sxs-lookup"><span data-stu-id="89653-180">**FindFirstFile** exported from Kernel32.dll.</span></span>  
  
    ```  
    HANDLE FindFirstFile(LPCTSTR lpFileName, LPWIN32_FIND_DATA lpFindFileData);  
    ```  
  
 <span data-ttu-id="89653-181">传递至函数的原始结构包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="89653-181">The original structure passed to the function contains the following elements:</span></span>  
  
```  
typedef struct _WIN32_FIND_DATA   
{  
  DWORD    dwFileAttributes;   
  FILETIME ftCreationTime;   
  FILETIME ftLastAccessTime;   
  FILETIME ftLastWriteTime;   
  DWORD    nFileSizeHigh;   
  DWORD    nFileSizeLow;   
  DWORD    dwReserved0;   
  DWORD    dwReserved1;   
  TCHAR    cFileName[ MAX_PATH ];   
  TCHAR    cAlternateFileName[ 14 ];   
} WIN32_FIND_DATA, *PWIN32_FIND_DATA;  
```  
  
 <span data-ttu-id="89653-182">在此示例中，`FindData` 类包含原始结构和嵌入结构中每个元素的对应数据成员。</span><span class="sxs-lookup"><span data-stu-id="89653-182">In this sample, the `FindData` class contains a corresponding data member for each element of the original structure and the embedded structure.</span></span> <span data-ttu-id="89653-183">如果存在 2 个原始字符缓冲区，类将替换字符串。</span><span class="sxs-lookup"><span data-stu-id="89653-183">In place of two original character buffers, the class substitutes strings.</span></span> <span data-ttu-id="89653-184">MarshalAsAttribute 将 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举设置为 ByValTStr，它用于标识非托管结构中出现的定长内联字符数组。</span><span class="sxs-lookup"><span data-stu-id="89653-184">**MarshalAsAttribute** sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged structures.</span></span>  
  
 <span data-ttu-id="89653-185">`LibWrap` 类包含 `FindFirstFile` 方法的托管原型，此方法将 `FindData` 类作为参数传递。</span><span class="sxs-lookup"><span data-stu-id="89653-185">The `LibWrap` class contains a managed prototype of the `FindFirstFile` method, which passes the `FindData` class as a parameter.</span></span> <span data-ttu-id="89653-186">此参数必须使用 <xref:System.Runtime.InteropServices.InAttribute> 和 <xref:System.Runtime.InteropServices.OutAttribute> 属性进行声明，因为作为引用类型的类默认传递为 In 参数。</span><span class="sxs-lookup"><span data-stu-id="89653-186">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="89653-187">声明原型</span><span class="sxs-lookup"><span data-stu-id="89653-187">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#17)]
 [!code-csharp[Conceptual.Interop.Marshaling#17](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#17)]
 [!code-vb[Conceptual.Interop.Marshaling#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#17)]  
  
### <a name="calling-functions"></a><span data-ttu-id="89653-188">调用函数</span><span class="sxs-lookup"><span data-stu-id="89653-188">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/findfile.cpp#18)]
 [!code-csharp[Conceptual.Interop.Marshaling#18](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/findfile.cs#18)]
 [!code-vb[Conceptual.Interop.Marshaling#18](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/findfile.vb#18)]  
  
## <a name="unions-sample"></a><span data-ttu-id="89653-189">“联合”示例</span><span class="sxs-lookup"><span data-stu-id="89653-189">Unions sample</span></span>  
 <span data-ttu-id="89653-190">此示例演示了如何将仅包含值类型的结构以及包含值类型和字符串的结构作为参数传递至需要联合的非托管函数。</span><span class="sxs-lookup"><span data-stu-id="89653-190">This sample demonstrates how to pass structures containing only value types, and structures containing a value type and a string as parameters to an unmanaged function expecting a union.</span></span> <span data-ttu-id="89653-191">联合是指可由两个或多个变量共享的内存位置。</span><span class="sxs-lookup"><span data-stu-id="89653-191">A union represents a memory location that can be shared by two or more variables.</span></span>  
  
 <span data-ttu-id="89653-192">“联合”示例使用以下非托管函数（与其原始函数声明一同显示）：</span><span class="sxs-lookup"><span data-stu-id="89653-192">The Unions sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="89653-193">从 PinvokeLib.dll 导出的 TestUnion。</span><span class="sxs-lookup"><span data-stu-id="89653-193">**TestUnion** exported from PinvokeLib.dll.</span></span>  
  
    ```  
    void TestUnion(MYUNION u, int type);  
    ```  
  
 <span data-ttu-id="89653-194">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) 是一种自定义的非托管库，包含上述函数和两个联合（MYUNION 和 MYUNION2）的实现。</span><span class="sxs-lookup"><span data-stu-id="89653-194">[PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) is a custom unmanaged library that contains an implementation for the previously listed function and two unions, **MYUNION** and **MYUNION2**.</span></span> <span data-ttu-id="89653-195">联合包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="89653-195">The unions contain the following elements:</span></span>  
  
```  
union MYUNION  
{  
    int number;  
    double d;  
}  
  
union MYUNION2  
{  
    int i;  
    char str[128];  
};  
```  
  
 <span data-ttu-id="89653-196">在托管代码中，将联合定义为结构。</span><span class="sxs-lookup"><span data-stu-id="89653-196">In managed code, unions are defined as structures.</span></span> <span data-ttu-id="89653-197">`MyUnion` 结构包含两个值类型（整数和双精度值），将其作为成员。</span><span class="sxs-lookup"><span data-stu-id="89653-197">The `MyUnion` structure contains two value types as its members: an integer and a double.</span></span> <span data-ttu-id="89653-198"><xref:System.Runtime.InteropServices.StructLayoutAttribute> 属性设置为控制每个数据成员的精确位置。</span><span class="sxs-lookup"><span data-stu-id="89653-198">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to control the precise position of each data member.</span></span> <span data-ttu-id="89653-199"><xref:System.Runtime.InteropServices.FieldOffsetAttribute> 属性提供联合的非托管表示形式中字段的物理位置。</span><span class="sxs-lookup"><span data-stu-id="89653-199">The <xref:System.Runtime.InteropServices.FieldOffsetAttribute> attribute provides the physical position of fields within the unmanaged representation of a union.</span></span> <span data-ttu-id="89653-200">请注意，这两个成员具有相同的偏移值，因此成员可以定义相同的内存块数。</span><span class="sxs-lookup"><span data-stu-id="89653-200">Notice that both members have the same offset values, so the members can define the same piece of memory.</span></span>  
  
 <span data-ttu-id="89653-201">`MyUnion2_1` 和 `MyUnion2_2` 分别包含值类型（整数）和字符串。</span><span class="sxs-lookup"><span data-stu-id="89653-201">`MyUnion2_1` and `MyUnion2_2` contain a value type (integer) and a string, respectively.</span></span> <span data-ttu-id="89653-202">在托管代码中，值类型和引用类型不允许重叠。</span><span class="sxs-lookup"><span data-stu-id="89653-202">In managed code, value types and reference types are not permitted to overlap.</span></span> <span data-ttu-id="89653-203">此示例使用方法重载以使调用方在调用同一个非托管函数时能够使用这两种类型。</span><span class="sxs-lookup"><span data-stu-id="89653-203">This sample uses method overloading to enable the caller to use both types when calling the same unmanaged function.</span></span> <span data-ttu-id="89653-204">`MyUnion2_1` 的布局是显式的且具有准确的偏移值。</span><span class="sxs-lookup"><span data-stu-id="89653-204">The layout of `MyUnion2_1` is explicit and has a precise offset value.</span></span> <span data-ttu-id="89653-205">与此相反，`MyUnion2_2` 的布局是按顺序的，因为不允许引用类型使用显式布局。</span><span class="sxs-lookup"><span data-stu-id="89653-205">In contrast, `MyUnion2_2` has a sequential layout, because explicit layouts are not permitted with reference types.</span></span> <span data-ttu-id="89653-206"><xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性将 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举设置为 ByValTStr，它用于标识在联合的非托管表示形式中出现的定长内联字符数组。</span><span class="sxs-lookup"><span data-stu-id="89653-206">The <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute sets the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration to **ByValTStr**, which is used to identify the inline, fixed-length character arrays that appear within the unmanaged representation of the union.</span></span>  
  
 <span data-ttu-id="89653-207">`LibWrap` 类包含 `TestUnion` 和 `TestUnion2` 方法的原型。</span><span class="sxs-lookup"><span data-stu-id="89653-207">The `LibWrap` class contains the prototypes for the `TestUnion` and `TestUnion2` methods.</span></span> <span data-ttu-id="89653-208">已重载 `TestUnion2` 以将 `MyUnion2_1` 或 `MyUnion2_2` 声明为参数。</span><span class="sxs-lookup"><span data-stu-id="89653-208">`TestUnion2` is overloaded to declare `MyUnion2_1` or `MyUnion2_2` as parameters.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="89653-209">声明原型</span><span class="sxs-lookup"><span data-stu-id="89653-209">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#28)]
 [!code-csharp[Conceptual.Interop.Marshaling#28](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#28)]
 [!code-vb[Conceptual.Interop.Marshaling#28](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#28)]  
  
### <a name="calling-functions"></a><span data-ttu-id="89653-210">调用函数</span><span class="sxs-lookup"><span data-stu-id="89653-210">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/unions.cpp#29)]
 [!code-csharp[Conceptual.Interop.Marshaling#29](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/unions.cs#29)]
 [!code-vb[Conceptual.Interop.Marshaling#29](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/unions.vb#29)]  
  
## <a name="systime-sample"></a><span data-ttu-id="89653-211">SysTime 示例</span><span class="sxs-lookup"><span data-stu-id="89653-211">SysTime sample</span></span>  
 <span data-ttu-id="89653-212">此示例演示了如何将指向类的指针传递到需要指向结构的指针的非托管函数。</span><span class="sxs-lookup"><span data-stu-id="89653-212">This sample demonstrates how to pass a pointer to a class to an unmanaged function that expects a pointer to a structure.</span></span>  
  
 <span data-ttu-id="89653-213">SysTime 示例使用以下非托管函数（与其其原始函数声明一同显示）：</span><span class="sxs-lookup"><span data-stu-id="89653-213">The SysTime sample uses the following unmanaged function, shown with its original function declaration:</span></span>  
  
-   <span data-ttu-id="89653-214">从 Kernel32.dll 导出的 GetSystemTime。</span><span class="sxs-lookup"><span data-stu-id="89653-214">**GetSystemTime** exported from Kernel32.dll.</span></span>  
  
    ```  
    VOID GetSystemTime(LPSYSTEMTIME lpSystemTime);  
    ```  
  
 <span data-ttu-id="89653-215">传递至函数的原始结构包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="89653-215">The original structure passed to the function contains the following elements:</span></span>  
  
```  
typedef struct _SYSTEMTIME {   
    WORD wYear;   
    WORD wMonth;   
    WORD wDayOfWeek;   
    WORD wDay;   
    WORD wHour;   
    WORD wMinute;   
    WORD wSecond;   
    WORD wMilliseconds;   
} SYSTEMTIME, *PSYSTEMTIME;  
```  
  
 <span data-ttu-id="89653-216">在此示例中，`SystemTime` 类包含原始结构中表示为类成员的元素。</span><span class="sxs-lookup"><span data-stu-id="89653-216">In this sample, the `SystemTime` class contains the elements of the original structure represented as class members.</span></span> <span data-ttu-id="89653-217">设置 <xref:System.Runtime.InteropServices.StructLayoutAttribute> 特性，以确保成员在内存中按照它们出现的顺序进行排列。</span><span class="sxs-lookup"><span data-stu-id="89653-217">The <xref:System.Runtime.InteropServices.StructLayoutAttribute> attribute is set to ensure that the members are arranged in memory sequentially, in the order in which they appear.</span></span>  
  
 <span data-ttu-id="89653-218">`LibWrap` 类包含 `GetSystemTime` 方法的托管原型，此方法在默认情况下将 `SystemTime` 类作为 In/Out 参数传递。</span><span class="sxs-lookup"><span data-stu-id="89653-218">The `LibWrap` class contains a managed prototype of the `GetSystemTime` method, which passes the `SystemTime` class as an In/Out parameter by default.</span></span> <span data-ttu-id="89653-219">此参数必须使用 <xref:System.Runtime.InteropServices.InAttribute> 和 <xref:System.Runtime.InteropServices.OutAttribute> 属性进行声明，因为作为引用类型的类默认传递为 In 参数。</span><span class="sxs-lookup"><span data-stu-id="89653-219">The parameter must be declared with the <xref:System.Runtime.InteropServices.InAttribute> and <xref:System.Runtime.InteropServices.OutAttribute> attributes because classes, which are reference types, are passed as In parameters by default.</span></span> <span data-ttu-id="89653-220">为使调用方接收结果，这些[方向特性](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))必须显式应用。</span><span class="sxs-lookup"><span data-stu-id="89653-220">For the caller to receive the results, these [directional attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100)) must be applied explicitly.</span></span> <span data-ttu-id="89653-221">`App` 类创建 `SystemTime` 类的新实例，并访问它的数据字段。</span><span class="sxs-lookup"><span data-stu-id="89653-221">The `App` class creates a new instance of the `SystemTime` class and accesses its data fields.</span></span>  
  
### <a name="code-samples"></a><span data-ttu-id="89653-222">代码示例</span><span class="sxs-lookup"><span data-stu-id="89653-222">Code Samples</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/systime.cpp#25)]
 [!code-csharp[Conceptual.Interop.Marshaling#25](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/systime.cs#25)]
 [!code-vb[Conceptual.Interop.Marshaling#25](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/systime.vb#25)]  
  
## <a name="outarrayofstructs-sample"></a><span data-ttu-id="89653-223">OutArrayOfStructs 示例</span><span class="sxs-lookup"><span data-stu-id="89653-223">OutArrayOfStructs sample</span></span>  
 <span data-ttu-id="89653-224">此示例显示如何将包含整数和字符串的结构数组作为 Out 参数传递到非托管函数。</span><span class="sxs-lookup"><span data-stu-id="89653-224">This sample shows how to pass an array of structures that contains integers and strings as Out parameters to an unmanaged function.</span></span>  
  
 <span data-ttu-id="89653-225">此示例演示如何通过使用 <xref:System.Runtime.InteropServices.Marshal> 类和使用不安全代码调用本机函数。</span><span class="sxs-lookup"><span data-stu-id="89653-225">This sample demonstrates how to call a native function by using the <xref:System.Runtime.InteropServices.Marshal> class and by using unsafe code.</span></span>  
  
 <span data-ttu-id="89653-226">此示例使用 [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)) 中定义（且位于源文件）的包装器函数和平台调用。</span><span class="sxs-lookup"><span data-stu-id="89653-226">This sample uses a wrapper functions and platform invokes defined in [PinvokeLib.dll](https://msdn.microsoft.com/library/5d1438d7-9946-489d-8ede-6c694a08f614(v=vs.100)), also provided in the source files.</span></span> <span data-ttu-id="89653-227">它使用 `TestOutArrayOfStructs` 函数和 `MYSTRSTRUCT2` 结构。</span><span class="sxs-lookup"><span data-stu-id="89653-227">It uses the `TestOutArrayOfStructs` function and the `MYSTRSTRUCT2` structure.</span></span> <span data-ttu-id="89653-228">结构包含以下元素：</span><span class="sxs-lookup"><span data-stu-id="89653-228">The structure contains the following elements:</span></span>  
  
```  
typedef struct _MYSTRSTRUCT2  
{  
   char* buffer;  
   UINT size;   
} MYSTRSTRUCT2;  
```  
  
 <span data-ttu-id="89653-229">`MyStruct` 类包含 ANSI 字符的字符串对象。</span><span class="sxs-lookup"><span data-stu-id="89653-229">The `MyStruct` class contains a string object of ANSI characters.</span></span> <span data-ttu-id="89653-230"><xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> 字段指定 ANSI 格式。</span><span class="sxs-lookup"><span data-stu-id="89653-230">The <xref:System.Runtime.InteropServices.DllImportAttribute.CharSet> field specifies ANSI format.</span></span> <span data-ttu-id="89653-231">`MyUnsafeStruct` 是一种包含 <xref:System.IntPtr> 类型（而非字符串）的结构。</span><span class="sxs-lookup"><span data-stu-id="89653-231">`MyUnsafeStruct`, is a structure containing an <xref:System.IntPtr> type instead of a string.</span></span>  
  
 <span data-ttu-id="89653-232">`LibWrap` 类包含已重载 `TestOutArrayOfStructs` 原型方法。</span><span class="sxs-lookup"><span data-stu-id="89653-232">The `LibWrap` class contains the overloaded `TestOutArrayOfStructs` prototype method.</span></span> <span data-ttu-id="89653-233">如果方法将指针声明为参数，则应使用 `unsafe` 关键字标记类。</span><span class="sxs-lookup"><span data-stu-id="89653-233">If a method declares a pointer as a parameter, the class should be marked with the `unsafe` keyword.</span></span> <span data-ttu-id="89653-234">因为 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 无法使用不安全代码，所以已重载方法、不安全修饰符和 `MyUnsafeStruct` 结构不是必需的。</span><span class="sxs-lookup"><span data-stu-id="89653-234">Because [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] cannot use unsafe code, the overloaded method, unsafe modifier, and the `MyUnsafeStruct` structure are unnecessary.</span></span>  
  
 <span data-ttu-id="89653-235">`App` 类实现 `UsingMarshaling` 方法，此方法执行传递数组所需的全部任务。</span><span class="sxs-lookup"><span data-stu-id="89653-235">The `App` class implements the `UsingMarshaling` method, which performs all the tasks necessary to pass the array.</span></span> <span data-ttu-id="89653-236">使用 `out`（Visual Basic 中的 `ByRef`）关键字标记数组，以指示数据从被调用方传递至调用方。</span><span class="sxs-lookup"><span data-stu-id="89653-236">The array is marked with the `out` (`ByRef` in Visual Basic) keyword to indicate that data passes from callee to caller.</span></span> <span data-ttu-id="89653-237">实现使用以下 <xref:System.Runtime.InteropServices.Marshal> 类方法：</span><span class="sxs-lookup"><span data-stu-id="89653-237">The implementation uses the following <xref:System.Runtime.InteropServices.Marshal> class methods:</span></span>  
  
-   <span data-ttu-id="89653-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A>，用于将数据从非托管缓冲区封送到托管对象。</span><span class="sxs-lookup"><span data-stu-id="89653-238"><xref:System.Runtime.InteropServices.Marshal.PtrToStructure%2A> to marshal data from the unmanaged buffer to a managed object.</span></span>  
  
-   <span data-ttu-id="89653-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A>用于释放为结构中的字符串保留的内存。</span><span class="sxs-lookup"><span data-stu-id="89653-239"><xref:System.Runtime.InteropServices.Marshal.DestroyStructure%2A> to release the memory reserved for strings in the structure.</span></span>  
  
-   <span data-ttu-id="89653-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A>用于释放为数组保留的内存。</span><span class="sxs-lookup"><span data-stu-id="89653-240"><xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> to release the memory reserved for the array.</span></span>  
  
 <span data-ttu-id="89653-241">正如上文所述，C# 允许不安全代码而 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 不允许。</span><span class="sxs-lookup"><span data-stu-id="89653-241">As previously mentioned, C# allows unsafe code and [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] does not.</span></span> <span data-ttu-id="89653-242">在 C# 示例中，`UsingUnsafePointer` 是一种替代性方法实现，使用指针（而非 <xref:System.Runtime.InteropServices.Marshal> 类）传递会包含 `MyUnsafeStruct` 结构的数组。</span><span class="sxs-lookup"><span data-stu-id="89653-242">In the C# sample, `UsingUnsafePointer` is an alternative method implementation that uses pointers instead of the <xref:System.Runtime.InteropServices.Marshal> class to pass back the array containing the `MyUnsafeStruct` structure.</span></span>  
  
### <a name="declaring-prototypes"></a><span data-ttu-id="89653-243">声明原型</span><span class="sxs-lookup"><span data-stu-id="89653-243">Declaring Prototypes</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#20)]
 [!code-csharp[Conceptual.Interop.Marshaling#20](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#20)]
 [!code-vb[Conceptual.Interop.Marshaling#20](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#20)]  
  
### <a name="calling-functions"></a><span data-ttu-id="89653-244">调用函数</span><span class="sxs-lookup"><span data-stu-id="89653-244">Calling Functions</span></span>  
 [!code-cpp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.interop.marshaling/cpp/outarrayofstructs.cpp#21)]
 [!code-csharp[Conceptual.Interop.Marshaling#21](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.interop.marshaling/cs/outarrayofstructs.cs#21)]
 [!code-vb[Conceptual.Interop.Marshaling#21](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.interop.marshaling/vb/outarrayofstructs.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="89653-245">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89653-245">See Also</span></span>  
 [<span data-ttu-id="89653-246">用平台调用封送数据</span><span class="sxs-lookup"><span data-stu-id="89653-246">Marshaling Data with Platform Invoke</span></span>](marshaling-data-with-platform-invoke.md)  
 <span data-ttu-id="89653-247">[平台调用数据类型](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="89653-247">[Platform Invoke Data Types](https://msdn.microsoft.com/library/16014d9f-d6bd-481e-83f0-df11377c550f(v=vs.100))</span></span>  
 [<span data-ttu-id="89653-248">封送处理字符串</span><span class="sxs-lookup"><span data-stu-id="89653-248">Marshaling Strings</span></span>](marshaling-strings.md)  
 <span data-ttu-id="89653-249">[封送类型数组](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="89653-249">[Marshaling Arrays of Types](https://msdn.microsoft.com/library/049b1c1b-228f-4445-88ec-91bc7fd4b1e8(v=vs.100))</span></span>
