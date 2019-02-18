---
title: 如何：手动创建包装器
ms.date: 03/30/2017
helpviewer_keywords:
- wrappers, creating manually
ms.assetid: cc2a70d8-6a58-4071-a8cf-ce28c018c09b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 62d11c5f098887bf26ab71c0d8d072972437210d
ms.sourcegitcommit: 30e2fe5cc4165aa6dde7218ec80a13def3255e98
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2019
ms.locfileid: "56220057"
---
# <a name="how-to-create-wrappers-manually"></a><span data-ttu-id="a44f2-102">如何：手动创建包装器</span><span class="sxs-lookup"><span data-stu-id="a44f2-102">How to: Create Wrappers Manually</span></span>
<span data-ttu-id="a44f2-103">如果决定在托管源代码中手动声明 COM 类型，则最佳的着手点是现有的接口定义语言 (IDL) 文件或类型库。</span><span class="sxs-lookup"><span data-stu-id="a44f2-103">If you decide to declare COM types manually in managed source code, the best place to start is with an existing Interface Definition Language (IDL) file or type library.</span></span> <span data-ttu-id="a44f2-104">不具备 IDL 文件或无法生成类型库文件时，可以通过创建托管的声明并将生成的程序集导出到类型库来模拟 COM 类型。</span><span class="sxs-lookup"><span data-stu-id="a44f2-104">When you do not have the IDL file or cannot generate a type library file, you can simulate the COM types by creating managed declarations and exporting the resulting assembly to a type library.</span></span>  
  
### <a name="to-simulate-com-types-from-managed-source"></a><span data-ttu-id="a44f2-105">从托管源模拟 COM 类型</span><span class="sxs-lookup"><span data-stu-id="a44f2-105">To simulate COM types from managed source</span></span>  
  
1.  <span data-ttu-id="a44f2-106">在符合公共语言规范 (CLS) 的语言中声明类型并编译文件。</span><span class="sxs-lookup"><span data-stu-id="a44f2-106">Declare the types in a language that is compliant with the Common Language Specification (CLS) and compile the file.</span></span>  
  
2.  <span data-ttu-id="a44f2-107">使用[类型库导出程序 (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md) 导出包含类型的程序集。</span><span class="sxs-lookup"><span data-stu-id="a44f2-107">Export the assembly containing the types with the [Type Library Exporter (Tlbexp.exe)](../tools/tlbexp-exe-type-library-exporter.md).</span></span>  
  
3.  <span data-ttu-id="a44f2-108">将导出的 COM 类型库用作声明面向 COM 托管类型的基础。</span><span class="sxs-lookup"><span data-stu-id="a44f2-108">Use the exported COM type library as a basis for declaring COM-oriented managed types.</span></span>  
  
### <a name="to-create-a-runtime-callable-wrapper-rcw"></a><span data-ttu-id="a44f2-109">创建运行时可调用包装器 (RCW)</span><span class="sxs-lookup"><span data-stu-id="a44f2-109">To create a runtime callable wrapper (RCW)</span></span>  
  
1.  <span data-ttu-id="a44f2-110">假设你有一个 IDL 文件或类型库文件，请决定要在自定义 RCW 中包含哪些类和接口。</span><span class="sxs-lookup"><span data-stu-id="a44f2-110">Assuming that you have an IDL file or type library file, decide which classes and interfaces you want to include in the custom RCW.</span></span> <span data-ttu-id="a44f2-111">可以排除不打算在应用程序中直接或间接使用的任何类型。</span><span class="sxs-lookup"><span data-stu-id="a44f2-111">You can exclude any types that you do not intend to use directly or indirectly in your application.</span></span>  
  
2.  <span data-ttu-id="a44f2-112">在符合 CLS 的语言中创建一个源文件，并声明类型。</span><span class="sxs-lookup"><span data-stu-id="a44f2-112">Create a source file in a CLS-compliant language and declare the types.</span></span> <span data-ttu-id="a44f2-113">有关导入转换过程的完整说明，请参阅[有关从类型库转换到程序集的摘要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="a44f2-113">See [Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100)) for a complete description of the import conversion process.</span></span> <span data-ttu-id="a44f2-114">实际上，创建自定义 RCW 时，需要手动执行由[类型库导入程序 (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md) 所提供的类型转换活动。</span><span class="sxs-lookup"><span data-stu-id="a44f2-114">Effectively, when you create a custom RCW, you are manually performing the type conversion activity provided by the [Type Library Importer (Tlbimp.exe)](../tools/tlbimp-exe-type-library-importer.md).</span></span> <span data-ttu-id="a44f2-115">下一章节的示例显示 IDL 或类型库文件中的类型以及它们在 C# 代码中的对应类型。</span><span class="sxs-lookup"><span data-stu-id="a44f2-115">The example in the next section shows types in an IDL or type library file and their corresponding types in C# code.</span></span>  
  
3.  <span data-ttu-id="a44f2-116">完成声明后，请像编译任何其他托管源代码一样编译此文件。</span><span class="sxs-lookup"><span data-stu-id="a44f2-116">When the declarations are complete, compile the file as you compile any other managed source code.</span></span>  
  
4.  <span data-ttu-id="a44f2-117">与使用 Tlbimp.exe 导入的类型相同，某些类型需要其他信息，你可以将其直接添加到自己的代码中。</span><span class="sxs-lookup"><span data-stu-id="a44f2-117">As with the types imported with Tlbimp.exe, some require additional information, which you can add directly to your code.</span></span> <span data-ttu-id="a44f2-118">有关详细信息，请参阅[如何：编辑互操作程序集](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))。</span><span class="sxs-lookup"><span data-stu-id="a44f2-118">For details, see [How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a44f2-119">示例</span><span class="sxs-lookup"><span data-stu-id="a44f2-119">Example</span></span>  
 <span data-ttu-id="a44f2-120">以下代码演示了 IDL 中的 `ISATest` 接口和 `SATest` 类以及 C# 源代码中相应类型的示例。</span><span class="sxs-lookup"><span data-stu-id="a44f2-120">The following code shows an example of the `ISATest` interface and `SATest` class in IDL and the corresponding types in C# source code.</span></span>  
  
 <span data-ttu-id="a44f2-121">**IDL 或类型库文件**</span><span class="sxs-lookup"><span data-stu-id="a44f2-121">**IDL or type library file**</span></span>  
  
```  
 [  
object,  
uuid(40A8C65D-2448-447A-B786-64682CBEF133),  
dual,  
helpstring("ISATest Interface"),  
pointer_default(unique)  
 ]  
interface ISATest : IDispatch  
 {  
[id(1), helpstring("method InSArray")]   
HRESULT InSArray([in] SAFEARRAY(int) *ppsa, [out,retval] int *pSum);  
 };  
 [  
uuid(116CCA1E-7E39-4515-9849-90790DA6431E),  
helpstring("SATest Class")  
 ]  
coclass SATest  
 {  
  [default] interface ISATest;  
 };  
```  
  
 <span data-ttu-id="a44f2-122">**托管源代码的包装器**</span><span class="sxs-lookup"><span data-stu-id="a44f2-122">**Wrapper in managed source code**</span></span>  
  
```csharp  
using System;  
using System.Runtime.InteropServices;  
using System.Runtime.CompilerServices;  
  
[assembly:Guid("E4A992B8-6F5C-442C-96E7-C4778924C753")]  
[assembly:ImportedFromTypeLib("SAServerLib")]  
namespace SAServer  
{  
 [ComImport]  
 [Guid("40A8C65D-2448-447A-B786-64682CBEF133")]  
 [TypeLibType(TypeLibTypeFlags.FLicensed)]  
 public interface ISATest  
 {  
  [DispId(1)]  
  //[MethodImpl(MethodImplOptions.InternalCall,  
  // MethodCodeType=MethodCodeType.Runtime)]  
  int InSArray( [MarshalAs(UnmanagedType.SafeArray,  
      SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }   
 [ComImport]  
 [Guid("116CCA1E-7E39-4515-9849-90790DA6431E")]  
 [ClassInterface(ClassInterfaceType.None)]  
 [TypeLibType(TypeLibTypeFlags.FCanCreate)]  
 public class SATest : ISATest  
 {  
  [DispId(1)]  
  [MethodImpl(MethodImplOptions.InternalCall,   
  MethodCodeType=MethodCodeType.Runtime)]  
  extern int ISATest.InSArray( [MarshalAs(UnmanagedType.SafeArray,   
  SafeArraySubType=VarEnum.VT_I4)] ref int[] param );  
 }  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="a44f2-123">请参阅</span><span class="sxs-lookup"><span data-stu-id="a44f2-123">See also</span></span>
- <span data-ttu-id="a44f2-124">[自定义运行时可调用包装器](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a44f2-124">[Customizing Runtime Callable Wrappers](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/e753eftz(v=vs.100))</span></span>
- <span data-ttu-id="a44f2-125">[COM 数据类型](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a44f2-125">[COM Data Types](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/sak564ww(v=vs.100))</span></span>
- <span data-ttu-id="a44f2-126">[如何：编辑互操作程序集](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a44f2-126">[How to: Edit Interop Assemblies](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/8zbc969t(v=vs.100))</span></span>
- <span data-ttu-id="a44f2-127">[有关从类型库转换到程序集的摘要](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="a44f2-127">[Type Library to Assembly Conversion Summary](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))</span></span>
- [<span data-ttu-id="a44f2-128">Tlbimp.exe（类型库导入程序）</span><span class="sxs-lookup"><span data-stu-id="a44f2-128">Tlbimp.exe (Type Library Importer)</span></span>](../tools/tlbimp-exe-type-library-importer.md)
- [<span data-ttu-id="a44f2-129">Tlbexp.exe（类型库导出程序）</span><span class="sxs-lookup"><span data-stu-id="a44f2-129">Tlbexp.exe (Type Library Exporter)</span></span>](../tools/tlbexp-exe-type-library-exporter.md)
