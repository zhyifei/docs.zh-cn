---
title: 数组的默认封送处理
ms.date: 03/30/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- interop marshaling, arrays
- arrays, interop marshaling
ms.assetid: 8a3cca8b-dd94-4e3d-ad9a-9ee7590654bc
caps.latest.revision: 19
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 84f4015fd9bc5eb2de11b71530115d20c583d21d
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2018
---
# <a name="default-marshaling-for-arrays"></a><span data-ttu-id="04bf6-102">数组的默认封送处理</span><span class="sxs-lookup"><span data-stu-id="04bf6-102">Default Marshaling for Arrays</span></span>
<span data-ttu-id="04bf6-103">在完全由托管代码组成的应用程序中，公共语言运行时将数组类型作为 In/Out 参数传递。</span><span class="sxs-lookup"><span data-stu-id="04bf6-103">In an application consisting entirely of managed code, the common language runtime passes array types as In/Out parameters.</span></span> <span data-ttu-id="04bf6-104">而互操作封送拆收器默认将数组作为 In 参数传递。</span><span class="sxs-lookup"><span data-stu-id="04bf6-104">In contrast, the interop marshaler passes an array as In parameters by default.</span></span>  
  
 <span data-ttu-id="04bf6-105">使用[固定优化](copying-and-pinning.md)，blittable 数组在与同一单元中的对象交互时，可能看上去像是作为 In/Out 参数运行。</span><span class="sxs-lookup"><span data-stu-id="04bf6-105">With [pinning optimization](copying-and-pinning.md), a blittable array can appear to operate as an In/Out parameter when interacting with objects in the same apartment.</span></span> <span data-ttu-id="04bf6-106">但是，如果随后将代码导出到用于生成跨计算机代理的类型库，且该库用于跨单元封送调用，则调用可还原为真正的 In 参数行为。</span><span class="sxs-lookup"><span data-stu-id="04bf6-106">However, if you later export the code to a type library used to generate the cross-machine proxy, and that library is used to marshal your calls across apartments, the calls can revert to true In parameter behavior.</span></span>  
  
 <span data-ttu-id="04bf6-107">数组本就很复杂，而托管数组和非托管数组之间的差异使它们比其他 blittable 类型具有更多信息。</span><span class="sxs-lookup"><span data-stu-id="04bf6-107">Arrays are complex by nature, and the distinctions between managed and unmanaged arrays warrant more information than other non-blittable types.</span></span> <span data-ttu-id="04bf6-108">本主题提供封送处理数组的以下信息：</span><span class="sxs-lookup"><span data-stu-id="04bf6-108">This topic provides the following information on marshaling arrays:</span></span>  
  
-   [<span data-ttu-id="04bf6-109">托管数组</span><span class="sxs-lookup"><span data-stu-id="04bf6-109">Managed Arrays</span></span>](#cpcondefaultmarshalingforarraysanchor1)  
  
-   [<span data-ttu-id="04bf6-110">非托管数组</span><span class="sxs-lookup"><span data-stu-id="04bf6-110">Unmanaged Arrays</span></span>](#cpcondefaultmarshalingforarraysanchor2)  
  
-   [<span data-ttu-id="04bf6-111">将数组参数传递给 .NET 代码</span><span class="sxs-lookup"><span data-stu-id="04bf6-111">Passing Array Parameters to .NET Code</span></span>](#cpcondefaultmarshalingforarraysanchor3)  
  
-   [<span data-ttu-id="04bf6-112">将数组传递给 COM</span><span class="sxs-lookup"><span data-stu-id="04bf6-112">Passing Arrays to COM</span></span>](#cpcondefaultmarshalingforarraysanchor4)  
  
<a name="cpcondefaultmarshalingforarraysanchor1"></a>   
## <a name="managed-arrays"></a><span data-ttu-id="04bf6-113">托管数组</span><span class="sxs-lookup"><span data-stu-id="04bf6-113">Managed Arrays</span></span>  
 <span data-ttu-id="04bf6-114">可以有各种托管数组类型；但是，<xref:System.Array?displayProperty=nameWithType> 类是所有数组类型的基类。</span><span class="sxs-lookup"><span data-stu-id="04bf6-114">Managed array types can vary; however, the <xref:System.Array?displayProperty=nameWithType> class is the base class of all array types.</span></span> <span data-ttu-id="04bf6-115">System.Array 类的属性可确定数组的秩、长度、下限和上限，其方法可用于访问、搜索、复制、创建数组以及对数组排序。</span><span class="sxs-lookup"><span data-stu-id="04bf6-115">The **System.Array** class has properties for determining the rank, length, and lower and upper bounds of an array, as well as methods for accessing, sorting, searching, copying, and creating arrays.</span></span>  
  
 <span data-ttu-id="04bf6-116">这些数组类型是动态类型，在基类库中未定义相应的静态类型。</span><span class="sxs-lookup"><span data-stu-id="04bf6-116">These array types are dynamic and do not have a corresponding static type defined in the base class library.</span></span> <span data-ttu-id="04bf6-117">将元素类型和秩的每一种组合视作不同类型的数组非常方便。</span><span class="sxs-lookup"><span data-stu-id="04bf6-117">It is convenient to think of each combination of element type and rank as a distinct type of array.</span></span> <span data-ttu-id="04bf6-118">因此，一维整数数组与一维 double 类型数组是不同的类型。</span><span class="sxs-lookup"><span data-stu-id="04bf6-118">Therefore, a one-dimensional array of integers is of a different type than a one-dimensional array of double types.</span></span> <span data-ttu-id="04bf6-119">同样，二维整数数组与一维整数数组也不同。</span><span class="sxs-lookup"><span data-stu-id="04bf6-119">Similarly a two-dimensional array of integers is different from a one-dimensional array of integers.</span></span> <span data-ttu-id="04bf6-120">比较类型时，不考虑数组界限。</span><span class="sxs-lookup"><span data-stu-id="04bf6-120">The bounds of the array are not considered when comparing types.</span></span>  
  
 <span data-ttu-id="04bf6-121">如下表所示，托管数组的所有实例都必须有特定的元素类型、秩和下限。</span><span class="sxs-lookup"><span data-stu-id="04bf6-121">As the following table shows, any instance of a managed array must be of a specific element type, rank, and lower bound.</span></span>  
  
|<span data-ttu-id="04bf6-122">托管数组类型</span><span class="sxs-lookup"><span data-stu-id="04bf6-122">Managed array type</span></span>|<span data-ttu-id="04bf6-123">元素类型</span><span class="sxs-lookup"><span data-stu-id="04bf6-123">Element type</span></span>|<span data-ttu-id="04bf6-124">级别</span><span class="sxs-lookup"><span data-stu-id="04bf6-124">Rank</span></span>|<span data-ttu-id="04bf6-125">下限</span><span class="sxs-lookup"><span data-stu-id="04bf6-125">Lower bound</span></span>|<span data-ttu-id="04bf6-126">签名表示法</span><span class="sxs-lookup"><span data-stu-id="04bf6-126">Signature notation</span></span>|  
|------------------------|------------------|----------|-----------------|------------------------|  
|<span data-ttu-id="04bf6-127">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="04bf6-127">**ELEMENT_TYPE_ARRAY**</span></span>|<span data-ttu-id="04bf6-128">由类型指定。</span><span class="sxs-lookup"><span data-stu-id="04bf6-128">Specified by type.</span></span>|<span data-ttu-id="04bf6-129">由秩指定。</span><span class="sxs-lookup"><span data-stu-id="04bf6-129">Specified by rank.</span></span>|<span data-ttu-id="04bf6-130">由界限视情况指定。</span><span class="sxs-lookup"><span data-stu-id="04bf6-130">Optionally specified by bounds.</span></span>|<span data-ttu-id="04bf6-131">*类型* **[** *n*，*m* **]**</span><span class="sxs-lookup"><span data-stu-id="04bf6-131">*type* **[** *n*,*m* **]**</span></span>|  
|<span data-ttu-id="04bf6-132">ELEMENT_TYPE_CLASS</span><span class="sxs-lookup"><span data-stu-id="04bf6-132">**ELEMENT_TYPE_CLASS**</span></span>|<span data-ttu-id="04bf6-133">未知</span><span class="sxs-lookup"><span data-stu-id="04bf6-133">Unknown</span></span>|<span data-ttu-id="04bf6-134">未知</span><span class="sxs-lookup"><span data-stu-id="04bf6-134">Unknown</span></span>|<span data-ttu-id="04bf6-135">未知</span><span class="sxs-lookup"><span data-stu-id="04bf6-135">Unknown</span></span>|<span data-ttu-id="04bf6-136">**System.Array**</span><span class="sxs-lookup"><span data-stu-id="04bf6-136">**System.Array**</span></span>|  
|<span data-ttu-id="04bf6-137">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="04bf6-137">**ELEMENT_TYPE_SZARRAY**</span></span>|<span data-ttu-id="04bf6-138">由类型指定。</span><span class="sxs-lookup"><span data-stu-id="04bf6-138">Specified by type.</span></span>|<span data-ttu-id="04bf6-139">1</span><span class="sxs-lookup"><span data-stu-id="04bf6-139">1</span></span>|<span data-ttu-id="04bf6-140">0</span><span class="sxs-lookup"><span data-stu-id="04bf6-140">0</span></span>|<span data-ttu-id="04bf6-141">*类型* **[** *n* **]**</span><span class="sxs-lookup"><span data-stu-id="04bf6-141">*type* **[** *n* **]**</span></span>|  
  
<a name="cpcondefaultmarshalingforarraysanchor2"></a>   
## <a name="unmanaged-arrays"></a><span data-ttu-id="04bf6-142">非托管数组</span><span class="sxs-lookup"><span data-stu-id="04bf6-142">Unmanaged Arrays</span></span>  
 <span data-ttu-id="04bf6-143">非托管数组是 COM 样式安全数组或 C 样式数组，其长度固定或可变。</span><span class="sxs-lookup"><span data-stu-id="04bf6-143">Unmanaged arrays are either COM-style safe arrays or C-style arrays with fixed or variable length.</span></span> <span data-ttu-id="04bf6-144">安全数组是自我描述的数组，带有关联数组数据的类型、秩和界限。</span><span class="sxs-lookup"><span data-stu-id="04bf6-144">Safe arrays are self-describing arrays that carry the type, rank, and bounds of the associated array data.</span></span> <span data-ttu-id="04bf6-145">C 样式数组是具有固定下限 0 的一维类型化数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-145">C-style arrays are one-dimensional typed arrays with a fixed lower bound of 0.</span></span> <span data-ttu-id="04bf6-146">封送处理服务对两种数组类型的支持均有限。</span><span class="sxs-lookup"><span data-stu-id="04bf6-146">The marshaling service has limited support for both types of arrays.</span></span>  
  
<a name="cpcondefaultmarshalingforarraysanchor3"></a>   
## <a name="passing-array-parameters-to-net-code"></a><span data-ttu-id="04bf6-147">将数组参数传递给 .NET 代码</span><span class="sxs-lookup"><span data-stu-id="04bf6-147">Passing Array Parameters to .NET Code</span></span>  
 <span data-ttu-id="04bf6-148">C 样式数组和安全数组都可以作为安全数组或 C 样式数组从非托管代码传递给 .NET 代码。</span><span class="sxs-lookup"><span data-stu-id="04bf6-148">Both C-style arrays and safe arrays can be passed to .NET code from unmanaged code as either a safe array or a C-style array.</span></span> <span data-ttu-id="04bf6-149">下表显示非托管类型值和导入的类型。</span><span class="sxs-lookup"><span data-stu-id="04bf6-149">The following table shows the unmanaged type value and the imported type.</span></span>  
  
|<span data-ttu-id="04bf6-150">非托管类型</span><span class="sxs-lookup"><span data-stu-id="04bf6-150">Unmanaged type</span></span>|<span data-ttu-id="04bf6-151">导入的类型</span><span class="sxs-lookup"><span data-stu-id="04bf6-151">Imported type</span></span>|  
|--------------------|-------------------|  
|<span data-ttu-id="04bf6-152">SafeArray( Type )</span><span class="sxs-lookup"><span data-stu-id="04bf6-152">**SafeArray(** *Type* **)**</span></span>|<span data-ttu-id="04bf6-153">ELEMENT_TYPE_SZARRAY \<ConvertedTyp>e</span><span class="sxs-lookup"><span data-stu-id="04bf6-153">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="04bf6-154">秩 = 1，下限 = 0。</span><span class="sxs-lookup"><span data-stu-id="04bf6-154">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="04bf6-155">只有在托管签名中提供大小时，才知道大小。</span><span class="sxs-lookup"><span data-stu-id="04bf6-155">Size is known only if provided in the managed signature.</span></span> <span data-ttu-id="04bf6-156">不满足秩 = 1 或下限 = 0 的安全数组不能作为 SZARRAY 封送。</span><span class="sxs-lookup"><span data-stu-id="04bf6-156">Safe arrays that are not rank = 1 or lower bound = 0 cannot be marshaled as **SZARRAY**.</span></span>|  
|<span data-ttu-id="04bf6-157">Type []</span><span class="sxs-lookup"><span data-stu-id="04bf6-157">*Type*  **[]**</span></span>|<span data-ttu-id="04bf6-158">ELEMENT_TYPE_SZARRAY \<ConvertedTyp>e</span><span class="sxs-lookup"><span data-stu-id="04bf6-158">**ELEMENT_TYPE_SZARRAY** **\<** *ConvertedType* **>**</span></span><br /><br /> <span data-ttu-id="04bf6-159">秩 = 1，下限 = 0。</span><span class="sxs-lookup"><span data-stu-id="04bf6-159">Rank = 1, lower bound = 0.</span></span> <span data-ttu-id="04bf6-160">只有在托管签名中提供大小时，才知道大小。</span><span class="sxs-lookup"><span data-stu-id="04bf6-160">Size is known only if provided in the managed signature.</span></span>|  
  
### <a name="safe-arrays"></a><span data-ttu-id="04bf6-161">安全数组</span><span class="sxs-lookup"><span data-stu-id="04bf6-161">Safe Arrays</span></span>  
 <span data-ttu-id="04bf6-162">从类型库将安全数组导入 .NET 程序集时，该数组转换为已知类型（例如 int）的一维数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-162">When a safe array is imported from a type library to a .NET assembly, the array is converted to a one-dimensional array of a known type (such as **int**).</span></span> <span data-ttu-id="04bf6-163">适用于参数的类型转换规则同样适用于数组元素。</span><span class="sxs-lookup"><span data-stu-id="04bf6-163">The same type conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="04bf6-164">例如，BSTR 类型的安全数组可变为托管字符串数组，而变体的安全数组可变为托管对象数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-164">For example, a safe array of **BSTR** types becomes a managed array of strings and a safe array of variants becomes a managed array of objects.</span></span> <span data-ttu-id="04bf6-165">从类型库中捕获 SAFEARRAY 元素类型并将它保存在 <xref:System.Runtime.InteropServices.UnmanagedType> 枚举的 SAFEARRAY 值中。</span><span class="sxs-lookup"><span data-stu-id="04bf6-165">The **SAFEARRAY** element type is captured from the type library and saved in the **SAFEARRAY** value of the <xref:System.Runtime.InteropServices.UnmanagedType> enumeration.</span></span>  
  
 <span data-ttu-id="04bf6-166">由于无法根据类型库确定安全数组的秩和界限，因此假定秩等于 1，下限等于 0。</span><span class="sxs-lookup"><span data-stu-id="04bf6-166">Because the rank and bounds of the safe array cannot be determined from the type library, the rank is assumed to equal 1 and the lower bound is assumed to equal 0.</span></span> <span data-ttu-id="04bf6-167">必须在由[类型库导入程序 (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) 生成的托管签名中定义秩和界限。</span><span class="sxs-lookup"><span data-stu-id="04bf6-167">The rank and bounds must be defined in the managed signature produced by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="04bf6-168">如果运行时传递给方法的秩不同，则会引发 <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException>。</span><span class="sxs-lookup"><span data-stu-id="04bf6-168">If the rank passed to the method at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayRankMismatchException> is thrown.</span></span> <span data-ttu-id="04bf6-169">如果运行时传递的数组的类型不同，则会引发 <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException>。</span><span class="sxs-lookup"><span data-stu-id="04bf6-169">If the type of the array passed at run time differs, a <xref:System.Runtime.InteropServices.SafeArrayTypeMismatchException> is thrown.</span></span> <span data-ttu-id="04bf6-170">下面的示例演示托管代码和非托管代码中的安全数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-170">The following example shows safe arrays in managed and unmanaged code.</span></span>  
  
 <span data-ttu-id="04bf6-171">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-171">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1([in] SAFEARRAY( int ) ar);  
HRESULT New2([in] SAFEARRAY( DATE ) ar);  
HRESULT New3([in, out] SAFEARRAY( BSTR ) *ar);  
```  
  
 <span data-ttu-id="04bf6-172">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-172">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_I4)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_DATE)> _   
   ar() As DateTime)  
Sub New3(ByRef <MarshalAs(UnmanagedType.SafeArray, SafeArraySubType:=VT_BSTR)> _   
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_I4)] int[] ar) ;  
void New2([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_DATE)]   
   DateTime[] ar);  
void New3([MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VT_BSTR)]   
   ref String[] ar);  
```  
  
 <span data-ttu-id="04bf6-173">如果修改由 Tlbimp.exe 产生的方法签名以指示元素类型 ELEMENT_TYPE_ARRAY 而非 ELEMENT_TYPE_SZARRAY，则可将多维或非零界限安全数组封送到托管代码中。</span><span class="sxs-lookup"><span data-stu-id="04bf6-173">Multidimensional, or nonzero-bound safe arrays, can be marshaled into managed code if the method signature produced by Tlbimp.exe is modified to indicate an element type of **ELEMENT_TYPE_ARRAY** instead of **ELEMENT_TYPE_SZARRAY**.</span></span> <span data-ttu-id="04bf6-174">或者，可将 /sysarray 开关与 Tlbimp.exe 一起使用，将所有数组作为 <xref:System.Array?displayProperty=nameWithType> 对象导入。</span><span class="sxs-lookup"><span data-stu-id="04bf6-174">Alternatively, you can use the **/sysarray** switch with Tlbimp.exe to import all arrays as <xref:System.Array?displayProperty=nameWithType> objects.</span></span> <span data-ttu-id="04bf6-175">如果已知正在传递的数组是多维数组，则可编辑由 Tlbimp.exe 生成的 Microsoft 中间语言 (MSIL) 代码，然后重新编译它。</span><span class="sxs-lookup"><span data-stu-id="04bf6-175">In cases where the array being passed is known to be multidimensional, you can edit the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompile it.</span></span> <span data-ttu-id="04bf6-176">有关如何修改 MSIL 代码的详细信息，请参阅[自定义运行时可调用包装器](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="04bf6-176">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100)).</span></span>  
  
### <a name="c-style-arrays"></a><span data-ttu-id="04bf6-177">C 样式数组</span><span class="sxs-lookup"><span data-stu-id="04bf6-177">C-Style Arrays</span></span>  
 <span data-ttu-id="04bf6-178">将 C 样式数组从类型库导入 .NET 程序集中时，数组被转换为 ELEMENT_TYPE_SZARRAY。</span><span class="sxs-lookup"><span data-stu-id="04bf6-178">When a C-style array is imported from a type library to a .NET assembly, the array is converted to **ELEMENT_TYPE_SZARRAY**.</span></span>  
  
 <span data-ttu-id="04bf6-179">数组元素类型根据类型库确定并在导入期间保留。</span><span class="sxs-lookup"><span data-stu-id="04bf6-179">The array element type is determined from the type library and preserved during the import.</span></span> <span data-ttu-id="04bf6-180">适用于参数的转换规则同样适用于数组元素。</span><span class="sxs-lookup"><span data-stu-id="04bf6-180">The same conversion rules that apply to parameters also apply to array elements.</span></span> <span data-ttu-id="04bf6-181">例如，LPStr 类型的数组变为字符串类型的数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-181">For example, an array of **LPStr** types becomes an array of **String** types.</span></span> <span data-ttu-id="04bf6-182">Tlbimp.exe 捕获数组元素类型并将 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性应用于该参数。</span><span class="sxs-lookup"><span data-stu-id="04bf6-182">Tlbimp.exe captures the array element type and applies the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute to the parameter.</span></span>  
  
 <span data-ttu-id="04bf6-183">假定数组秩等于 1。</span><span class="sxs-lookup"><span data-stu-id="04bf6-183">The array rank is assumed to equal 1.</span></span> <span data-ttu-id="04bf6-184">如果秩大于 1，则将按列主序将数组作为一维数组封送。</span><span class="sxs-lookup"><span data-stu-id="04bf6-184">If the rank is greater than 1, the array is marshaled as a one-dimensional array in column-major order.</span></span> <span data-ttu-id="04bf6-185">下限始终等于 0。</span><span class="sxs-lookup"><span data-stu-id="04bf6-185">The lower bound always equals 0.</span></span>  
  
 <span data-ttu-id="04bf6-186">类型库可包含定长数组或变长数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-186">Type libraries can contain arrays of fixed or variable length.</span></span> <span data-ttu-id="04bf6-187">Tlbimp.exe 只能从类型库中导入定长数组，这是因为类型库缺少封送变长数组所需的信息。</span><span class="sxs-lookup"><span data-stu-id="04bf6-187">Tlbimp.exe can import only fixed-length arrays from type libraries because type libraries lack the information needed to marshal variable-length arrays.</span></span> <span data-ttu-id="04bf6-188">对于定长数组，从类型库导入大小，并在应用于参数的 MarshalAsAttribute 中捕获大小。</span><span class="sxs-lookup"><span data-stu-id="04bf6-188">With fixed-length arrays, the size is imported from the type library and captured in the **MarshalAsAttribute** that is applied to the parameter.</span></span>  
  
 <span data-ttu-id="04bf6-189">必须手动定义含变长数组的类型库，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="04bf6-189">You must manually define type libraries containing variable-length arrays, as shown in the following example.</span></span>  
  
 <span data-ttu-id="04bf6-190">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-190">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1(int ar[10]);  
HRESULT New2(double ar[10][20]);  
HRESULT New3(LPWStr ar[10]);  
```  
  
 <span data-ttu-id="04bf6-191">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-191">**Managed signature**</span></span>  
  
```vb  
Sub New1(<MarshalAs(UnmanagedType.LPArray, SizeConst=10)> _  
   ar() As Integer)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, SizeConst=200)> _  
   ar() As Double)  
Sub New2(<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)> _  
   ar() As String)  
```  
  
```csharp  
void New1([MarshalAs(UnmanagedType.LPArray, SizeConst=10)] int[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray, SizeConst=200)] double[] ar);  
void New2([MarshalAs(UnmanagedType.LPArray,   
   ArraySubType=UnmanagedType.LPWStr, SizeConst=10)] String[] ar);  
```  
  
 <span data-ttu-id="04bf6-192">虽然可将 size_is 或 length_is 属性应用于接口定义语言 (IDL) 源中的数组，以便将大小传达给客户端，但是 Microsoft 接口定义语言 (MIDL) 编译器不会将该信息传送到类型库。</span><span class="sxs-lookup"><span data-stu-id="04bf6-192">Although you can apply the **size_is** or **length_is** attributes to an array in Interface Definition Language (IDL) source to convey the size to a client, the Microsoft Interface Definition Language (MIDL) compiler does not propagate that information to the type library.</span></span> <span data-ttu-id="04bf6-193">如果不知道大小，互操作封送处理服务就无法封送数组元素。</span><span class="sxs-lookup"><span data-stu-id="04bf6-193">Without knowing the size, the interop marshaling service cannot marshal the array elements.</span></span> <span data-ttu-id="04bf6-194">因此，将变长数组作为引用参数导入。</span><span class="sxs-lookup"><span data-stu-id="04bf6-194">Consequently, variable-length arrays are imported as reference arguments.</span></span> <span data-ttu-id="04bf6-195">例如：</span><span class="sxs-lookup"><span data-stu-id="04bf6-195">For example:</span></span>  
  
 <span data-ttu-id="04bf6-196">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-196">**Unmanaged signature**</span></span>  
  
```  
HRESULT New1(int ar[]);  
HRESULT New2(int ArSize, [size_is(ArSize)] double ar[]);  
HRESULT New3(int ElemCnt, [length_is(ElemCnt)] LPStr ar[]);  
```  
  
 <span data-ttu-id="04bf6-197">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-197">**Managed signature**</span></span>  
  
```vb  
Sub New1(ByRef ar As Integer)  
Sub New2(ByRef ar As Double)  
Sub New3(ByRef ar As String)  
```  
  
```csharp  
void New1(ref int ar);    
void New2(ref double ar);    
void New3(ref String ar);   
```  
  
 <span data-ttu-id="04bf6-198">编辑由 Tlbimp.exe 生成的 Microsoft 中间语言 (MSIL) 代码，再重新编译该代码，即可向封送拆收器提供数组大小。</span><span class="sxs-lookup"><span data-stu-id="04bf6-198">You can provide the marshaler with the array size by editing the Microsoft intermediate language (MSIL) code produced by Tlbimp.exe and then recompiling it.</span></span> <span data-ttu-id="04bf6-199">有关如何修改 MSIL 代码的详细信息，请参阅[自定义运行时可调用包装器](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="04bf6-199">For details about how to modify MSIL code, see [Customizing Runtime Callable Wrappers](https://msdn.microsoft.com/library/4652beaf-77d0-4f37-9687-ca193288c0be(v=vs.100)).</span></span> <span data-ttu-id="04bf6-200">要指示数组中的元素数，请采用以下任一方式将 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 类型应用于托管方法定义的数组参数：</span><span class="sxs-lookup"><span data-stu-id="04bf6-200">To indicate the number of elements in the array, apply the <xref:System.Runtime.InteropServices.MarshalAsAttribute> type to the array parameter of the managed method definition in one of the following ways:</span></span>  
  
-   <span data-ttu-id="04bf6-201">标识含数组中的元素数的另一个参数。</span><span class="sxs-lookup"><span data-stu-id="04bf6-201">Identify another parameter that contains the number of elements in the array.</span></span> <span data-ttu-id="04bf6-202">按位置标识参数，从第一个参数开始，将第一个参数标识为数字 0。</span><span class="sxs-lookup"><span data-stu-id="04bf6-202">The parameters are identified by position, starting with the first parameter as number 0.</span></span>     
  
    ```vb  
    Sub [New](ElemCnt As Integer, _  
       \<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       int ElemCnt,   
       [MarshalAs(UnmanagedType.LPArray, SizeParamIndex=0)] int[] ar );  
    ```  
  
-   <span data-ttu-id="04bf6-203">将数组大小定义为常数。</span><span class="sxs-lookup"><span data-stu-id="04bf6-203">Define the size of the array as a constant.</span></span> <span data-ttu-id="04bf6-204">例如：</span><span class="sxs-lookup"><span data-stu-id="04bf6-204">For example:</span></span>  
  
    ```vb  
    Sub [New](\<MarshalAs(UnmanagedType.LPArray, SizeConst:=128)> _  
       ar() As Integer)  
    ```  
  
    ```csharp  
    void New(  
       [MarshalAs(UnmanagedType.LPArray, SizeConst=128)] int[] ar );  
    ```  
  
 <span data-ttu-id="04bf6-205">将数组从非托管代码封送到托管代码时，封送拆收器检查与参数关联的 MarshalAsAttribute 以确定数组大小。</span><span class="sxs-lookup"><span data-stu-id="04bf6-205">When marshaling arrays from unmanaged code to managed code, the marshaler checks the **MarshalAsAttribute** associated with the parameter to determine the array size.</span></span> <span data-ttu-id="04bf6-206">如果未指定数组大小，则只封送一个元素。</span><span class="sxs-lookup"><span data-stu-id="04bf6-206">If the array size is not specified, only one element is marshaled.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="04bf6-207">将托管数组封送到非托管代码不会受 MarshalAsAttribute 的影响。</span><span class="sxs-lookup"><span data-stu-id="04bf6-207">The **MarshalAsAttribute** has no effect on marshaling managed arrays to unmanaged code.</span></span> <span data-ttu-id="04bf6-208">在该方向上，数组大小通过检查确定。</span><span class="sxs-lookup"><span data-stu-id="04bf6-208">In that direction, the array size is determined by examination.</span></span> <span data-ttu-id="04bf6-209">无法封送托管数组的子集。</span><span class="sxs-lookup"><span data-stu-id="04bf6-209">There is no way to marshal a subset of a managed array.</span></span>  
  
 <span data-ttu-id="04bf6-210">互操作封送拆收器使用 CoTaskMemAlloc 和 CoTaskMemFree 方法分配和检索内存。</span><span class="sxs-lookup"><span data-stu-id="04bf6-210">The interop marshaler uses the **CoTaskMemAlloc** and **CoTaskMemFree** methods to allocate and retrieve memory.</span></span> <span data-ttu-id="04bf6-211">非托管代码所执行的内存分配也必须使用这些方法。</span><span class="sxs-lookup"><span data-stu-id="04bf6-211">Memory allocation performed by unmanaged code must also use these methods.</span></span>  
  
<a name="cpcondefaultmarshalingforarraysanchor4"></a>   
## <a name="passing-arrays-to-com"></a><span data-ttu-id="04bf6-212">将数组传递给 COM</span><span class="sxs-lookup"><span data-stu-id="04bf6-212">Passing Arrays to COM</span></span>  
 <span data-ttu-id="04bf6-213">所有托管数组类型都可以从托管代码传递给非托管代码。</span><span class="sxs-lookup"><span data-stu-id="04bf6-213">All managed array types can be passed to unmanaged code from managed code.</span></span> <span data-ttu-id="04bf6-214">根据托管类型和应用于它的属性，可将数组作为安全数组或 C 样式数组进行访问，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="04bf6-214">Depending on the managed type and the attributes applied to it, the array can be accessed as a safe array or a C-style array, as shown in the following table.</span></span>  
  
|<span data-ttu-id="04bf6-215">托管数组类型</span><span class="sxs-lookup"><span data-stu-id="04bf6-215">Managed array type</span></span>|<span data-ttu-id="04bf6-216">导出结果</span><span class="sxs-lookup"><span data-stu-id="04bf6-216">Exported as</span></span>|  
|------------------------|-----------------|  
|<span data-ttu-id="04bf6-217">ELEMENT_TYPE_SZARRAY \< type ></span><span class="sxs-lookup"><span data-stu-id="04bf6-217">**ELEMENT_TYPE_SZARRAY** **\<** *type* **>**</span></span>|<span data-ttu-id="04bf6-218"><xref:System.Runtime.InteropServices.UnmanagedType> .SafeArray( *type* **)**</span><span class="sxs-lookup"><span data-stu-id="04bf6-218"><xref:System.Runtime.InteropServices.UnmanagedType> **.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="04bf6-219">UnmanagedType.LPArray</span><span class="sxs-lookup"><span data-stu-id="04bf6-219">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="04bf6-220">签名中提供了类型。</span><span class="sxs-lookup"><span data-stu-id="04bf6-220">Type is provided in the signature.</span></span> <span data-ttu-id="04bf6-221">秩始终为 1，下限始终为 0。</span><span class="sxs-lookup"><span data-stu-id="04bf6-221">Rank is always 1, lower bound is always 0.</span></span> <span data-ttu-id="04bf6-222">在运行时大小始终为已知。</span><span class="sxs-lookup"><span data-stu-id="04bf6-222">Size is always known at run time.</span></span>|  
|<span data-ttu-id="04bf6-223">ELEMENT_TYPE_ARRAY \< type > \< rank >[ \<bounds> ]</span><span class="sxs-lookup"><span data-stu-id="04bf6-223">**ELEMENT_TYPE_ARRAY** **\<** *type* **>** **\<** *rank* **>**[**\<** *bounds* **>**]</span></span>|<span data-ttu-id="04bf6-224">UnmanagedType.SafeArray( type )</span><span class="sxs-lookup"><span data-stu-id="04bf6-224">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="04bf6-225">UnmanagedType.LPArray</span><span class="sxs-lookup"><span data-stu-id="04bf6-225">**UnmanagedType.LPArray**</span></span><br /><br /> <span data-ttu-id="04bf6-226">签名中提供了类型、秩和界限。</span><span class="sxs-lookup"><span data-stu-id="04bf6-226">Type, rank, bounds are provided in the signature.</span></span> <span data-ttu-id="04bf6-227">在运行时大小始终为已知。</span><span class="sxs-lookup"><span data-stu-id="04bf6-227">Size is always known at run time.</span></span>|  
|<span data-ttu-id="04bf6-228">ELEMENT_TYPE_CLASS \<<xref:System.Array?displayProperty=nameWithType>></span><span class="sxs-lookup"><span data-stu-id="04bf6-228">**ELEMENT_TYPE_CLASS** **\<**<xref:System.Array?displayProperty=nameWithType>**>**</span></span>|<span data-ttu-id="04bf6-229">UT_Interface</span><span class="sxs-lookup"><span data-stu-id="04bf6-229">**UT_Interface**</span></span><br /><br /> <span data-ttu-id="04bf6-230">UnmanagedType.SafeArray( type )</span><span class="sxs-lookup"><span data-stu-id="04bf6-230">**UnmanagedType.SafeArray(** *type* **)**</span></span><br /><br /> <span data-ttu-id="04bf6-231">在运行时类型、秩、界限和大小始终为已知。</span><span class="sxs-lookup"><span data-stu-id="04bf6-231">Type, rank, bounds, and size are always known at run time.</span></span>|  
  
 <span data-ttu-id="04bf6-232">在与含有 LPSTR 或 LPWSTR 的结构数组相关的 OLE 自动化中，存在一项限制。</span><span class="sxs-lookup"><span data-stu-id="04bf6-232">There is a limitation in OLE Automation relating to arrays of structures that contain LPSTR or LPWSTR.</span></span>  <span data-ttu-id="04bf6-233">因此，必须将 String 字段作为 UnmanagedType.BSTR 封送。</span><span class="sxs-lookup"><span data-stu-id="04bf6-233">Therefore, **String** fields have to be marshaled as **UnmanagedType.BSTR**.</span></span> <span data-ttu-id="04bf6-234">否则，将引发异常。</span><span class="sxs-lookup"><span data-stu-id="04bf6-234">Otherwise, an exception will be thrown.</span></span>  
  
### <a name="elementtypeszarray"></a><span data-ttu-id="04bf6-235">ELEMENT_TYPE_SZARRAY</span><span class="sxs-lookup"><span data-stu-id="04bf6-235">ELEMENT_TYPE_SZARRAY</span></span>  
 <span data-ttu-id="04bf6-236">将包含 ELEMENT_TYPE_SZARRAY 参数（一维数组）的方法从 .NET 程序集导出到类型库时，会将该数组参数转换为给定类型的 SAFEARRAY。</span><span class="sxs-lookup"><span data-stu-id="04bf6-236">When a method containing an **ELEMENT_TYPE_SZARRAY** parameter (one-dimensional array) is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="04bf6-237">同样的转换规则也适用于数组元素类型。</span><span class="sxs-lookup"><span data-stu-id="04bf6-237">The same conversion rules apply to the array element types.</span></span> <span data-ttu-id="04bf6-238">自动将托管数组的内容从托管内存复制到 SAFEARRAY 中。</span><span class="sxs-lookup"><span data-stu-id="04bf6-238">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="04bf6-239">例如：</span><span class="sxs-lookup"><span data-stu-id="04bf6-239">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="04bf6-240">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-240">Managed signature</span></span>  
  
```vb  
Sub [New](ar() As Long)  
Sub [New](ar() As String)  
```  
  
```csharp  
void New(long[] ar );  
void New(String[] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="04bf6-241">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-241">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="04bf6-242">安全数组的秩始终为 1，下限始终为 0。</span><span class="sxs-lookup"><span data-stu-id="04bf6-242">The rank of the safe arrays is always 1 and the lower bound is always 0.</span></span> <span data-ttu-id="04bf6-243">大小在运行时由所传递的托管数组的大小确定。</span><span class="sxs-lookup"><span data-stu-id="04bf6-243">The size is determined at run time by the size of the managed array being passed.</span></span>  
  
 <span data-ttu-id="04bf6-244">还可以通过使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性将数组作为 C 样式数组封送。</span><span class="sxs-lookup"><span data-stu-id="04bf6-244">The array can also be marshaled as a C-style array by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="04bf6-245">例如：</span><span class="sxs-lookup"><span data-stu-id="04bf6-245">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="04bf6-246">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-246">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As Long, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPArray, _  
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar() As String, size as Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   long [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, SizeParamIndex=1)]   
   String [] ar, int size );  
void New([MarshalAs(UnmanagedType.LPArray, ArraySubType=   
   UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="04bf6-247">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-247">Unmanaged signature</span></span>  
  
```  
HRESULT New(long ar[]);   
HRESULT New(BSTR ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="04bf6-248">虽然封送拆收器具有封送数组所需的长度信息，但通常会将数组长度作为单独的参数传递，以便将长度传达给被调用方。</span><span class="sxs-lookup"><span data-stu-id="04bf6-248">Although the marshaler has the length information needed to marshal the array, the array length is usually passed as a separate argument to convey the length to the callee.</span></span>  
  
### <a name="elementtypearray"></a><span data-ttu-id="04bf6-249">ELEMENT_TYPE_ARRAY</span><span class="sxs-lookup"><span data-stu-id="04bf6-249">ELEMENT_TYPE_ARRAY</span></span>  
 <span data-ttu-id="04bf6-250">将包含 ELEMENT_TYPE_ARRAY 参数的方法从 .NET 程序集导出到类型库时，会将该数组参数转换为给定类型的 SAFEARRAY。</span><span class="sxs-lookup"><span data-stu-id="04bf6-250">When a method containing an **ELEMENT_TYPE_ARRAY** parameter is exported from a .NET assembly to a type library, the array parameter is converted to a **SAFEARRAY** of a given type.</span></span> <span data-ttu-id="04bf6-251">自动将托管数组的内容从托管内存复制到 SAFEARRAY 中。</span><span class="sxs-lookup"><span data-stu-id="04bf6-251">The contents of the managed array are automatically copied from managed memory into the **SAFEARRAY**.</span></span> <span data-ttu-id="04bf6-252">例如：</span><span class="sxs-lookup"><span data-stu-id="04bf6-252">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="04bf6-253">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-253">Managed signature</span></span>  
  
```vb  
Sub [New](ar(,) As Long)  
Sub [New](ar(,) As String)  
```  
  
```csharp  
void New( long [,] ar );  
void New( String [,] ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="04bf6-254">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-254">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] SAFEARRAY( long ) ar);   
HRESULT New([in] SAFEARRAY( BSTR ) ar);  
```  
  
 <span data-ttu-id="04bf6-255">安全数组的秩、大小和界限在运行时由托管数组的特征确定。</span><span class="sxs-lookup"><span data-stu-id="04bf6-255">The rank, size, and bounds of the safe arrays are determined at run time by the characteristics of the managed array.</span></span>  
  
 <span data-ttu-id="04bf6-256">还可以通过应用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性将数组作为 C 样式数组封送。</span><span class="sxs-lookup"><span data-stu-id="04bf6-256">The array can also be marshaled as a C-style array by applying the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="04bf6-257">例如：</span><span class="sxs-lookup"><span data-stu-id="04bf6-257">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="04bf6-258">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-258">Managed signature</span></span>  
  
```vb  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex:=1)> _  
   ar(,) As Long, size As Integer)  
Sub [New](<MarshalAs(UnmanagedType.LPARRAY, _  
   ArraySubType:=UnmanagedType.LPStr, SizeParamIndex:=1)> _  
   ar(,) As String, size As Integer)  
```  
  
```csharp  
void New([MarshalAs(UnmanagedType.LPARRAY, SizeParamIndex=1)]   
   long [,] ar, int size );  
void New([MarshalAs(UnmanagedType.LPARRAY,   
   ArraySubType= UnmanagedType.LPStr, SizeParamIndex=1)]   
   String [,] ar, int size );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="04bf6-259">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-259">Unmanaged signature</span></span>  
  
```  
HRESULT New(long ar[]);   
HRESULT New(LPStr ar[]);  
```  
  
 <span data-ttu-id="04bf6-260">无法封送嵌套数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-260">Nested arrays cannot be marshaled.</span></span> <span data-ttu-id="04bf6-261">例如，使用[类型库导出程序 (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) 进行导出时，以下签名将生成错误。</span><span class="sxs-lookup"><span data-stu-id="04bf6-261">For example, the following signature generates an error when exported with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="04bf6-262">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-262">Managed signature</span></span>  
  
```vb  
Sub [New](ar()()() As Long)  
```  
  
```csharp  
void New(long [][][] ar );  
```  
  
### <a name="elementtypeclass-systemarray"></a><span data-ttu-id="04bf6-263">ELEMENT_TYPE_CLASS \<System.Array></span><span class="sxs-lookup"><span data-stu-id="04bf6-263">ELEMENT_TYPE_CLASS \<System.Array></span></span>  
 <span data-ttu-id="04bf6-264">将包含 <xref:System.Array?displayProperty=nameWithType> 参数的方法从 .NET 程序集导出到类型库时，会将该数组参数转换为 _Array 接口。</span><span class="sxs-lookup"><span data-stu-id="04bf6-264">When a method containing a <xref:System.Array?displayProperty=nameWithType> parameter is exported from a .NET assembly to a type library, the array parameter is converted to an **_Array** interface.</span></span> <span data-ttu-id="04bf6-265">只能通过 _Array 接口的方法和属性访问托管数组的内容。</span><span class="sxs-lookup"><span data-stu-id="04bf6-265">The contents of the managed array are accessible only through the methods and properties of the **_Array** interface.</span></span> <span data-ttu-id="04bf6-266">还可通过使用 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 属性将 System.Array 作为 SAFEARRAY 封送。</span><span class="sxs-lookup"><span data-stu-id="04bf6-266">**System.Array** can also be marshaled as a **SAFEARRAY** by using the <xref:System.Runtime.InteropServices.MarshalAsAttribute> attribute.</span></span> <span data-ttu-id="04bf6-267">作为安全数组封送时，将数组元素视作变体封送。</span><span class="sxs-lookup"><span data-stu-id="04bf6-267">When marshaled as a safe array, the array elements are marshaled as variants.</span></span> <span data-ttu-id="04bf6-268">例如：</span><span class="sxs-lookup"><span data-stu-id="04bf6-268">For example:</span></span>  
  
#### <a name="managed-signature"></a><span data-ttu-id="04bf6-269">托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-269">Managed signature</span></span>  
  
```vb  
Sub New1( ar As System.Array )  
Sub New2( <MarshalAs(UnmanagedType.Safe array)> ar As System.Array )  
```  
  
```csharp  
void New1( System.Array ar );  
void New2( [MarshalAs(UnmanagedType.Safe array)] System.Array ar );  
```  
  
#### <a name="unmanaged-signature"></a><span data-ttu-id="04bf6-270">非托管的签名</span><span class="sxs-lookup"><span data-stu-id="04bf6-270">Unmanaged signature</span></span>  
  
```  
HRESULT New([in] _Array *ar);   
HRESULT New([in] SAFEARRAY(VARIANT) ar);  
```  
  
### <a name="arrays-within-structures"></a><span data-ttu-id="04bf6-271">结构中的数组</span><span class="sxs-lookup"><span data-stu-id="04bf6-271">Arrays within Structures</span></span>  
 <span data-ttu-id="04bf6-272">非托管结构可包含嵌入数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-272">Unmanaged structures can contain embedded arrays.</span></span> <span data-ttu-id="04bf6-273">默认情况下，将这些嵌入数组字段作为 SAFEARRAY 封送。</span><span class="sxs-lookup"><span data-stu-id="04bf6-273">By default, these embedded array fields are marshaled as a SAFEARRAY.</span></span> <span data-ttu-id="04bf6-274">在以下示例中，`s1` 是直接在结构本身中分配的嵌入数组。</span><span class="sxs-lookup"><span data-stu-id="04bf6-274">In the following example, `s1` is an embedded array that is allocated directly within the structure itself.</span></span>  
  
#### <a name="unmanaged-representation"></a><span data-ttu-id="04bf6-275">非托管表示形式</span><span class="sxs-lookup"><span data-stu-id="04bf6-275">Unmanaged representation</span></span>  
  
```  
struct MyStruct {  
    short s1[128];  
}  
```  
  
 <span data-ttu-id="04bf6-276">数组可作为 <xref:System.Runtime.InteropServices.UnmanagedType> 封送，这需要设置 <xref:System.Runtime.InteropServices.MarshalAsAttribute> 字段。</span><span class="sxs-lookup"><span data-stu-id="04bf6-276">Arrays can be marshaled as <xref:System.Runtime.InteropServices.UnmanagedType>, which requires you to set the <xref:System.Runtime.InteropServices.MarshalAsAttribute> field.</span></span> <span data-ttu-id="04bf6-277">只能将大小设置为常数。</span><span class="sxs-lookup"><span data-stu-id="04bf6-277">The size can be set only as a constant.</span></span> <span data-ttu-id="04bf6-278">以下代码演示 `MyStruct` 的相应托管定义。</span><span class="sxs-lookup"><span data-stu-id="04bf6-278">The following code shows the corresponding managed definition of `MyStruct`.</span></span>  
  
```vb  
Public Structure <StructLayout(LayoutKind.Sequential)> MyStruct  
   Public <MarshalAs(UnmanagedType.ByValArray, SizeConst := 128)> _  
     s1() As Short  
End Structure  
```  
  
```csharp  
[StructLayout(LayoutKind.Sequential)]  
public struct MyStruct {  
   [MarshalAs(UnmanagedType.ByValArray, SizeConst=128)] public short[] s1;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="04bf6-279">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04bf6-279">See Also</span></span>  
 [<span data-ttu-id="04bf6-280">默认封送处理行为</span><span class="sxs-lookup"><span data-stu-id="04bf6-280">Default Marshaling Behavior</span></span>](default-marshaling-behavior.md)  
 [<span data-ttu-id="04bf6-281">可直接复制到本机结构中的类型和非直接复制到本机结构中的类型</span><span class="sxs-lookup"><span data-stu-id="04bf6-281">Blittable and Non-Blittable Types</span></span>](blittable-and-non-blittable-types.md)  
 <span data-ttu-id="04bf6-282">[方向特性](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="04bf6-282">[Directional Attributes](https://msdn.microsoft.com/library/241ac5b5-928e-4969-8f58-1dbc048f9ea2(v=vs.100))</span></span>  
 [<span data-ttu-id="04bf6-283">复制和锁定</span><span class="sxs-lookup"><span data-stu-id="04bf6-283">Copying and Pinning</span></span>](copying-and-pinning.md)
