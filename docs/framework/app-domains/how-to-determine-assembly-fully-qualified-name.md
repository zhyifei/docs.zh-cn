---
title: 如何：确定程序集的完全限定的名称
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- names [.NET Framework], fully qualified type names
- names [.NET Framework], assemblies
- assemblies [.NET Framework], names
ms.assetid: 009dae23-e1f6-4a64-9a9a-32e4c34802b0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: bb5978859ba25e1595ac3da7a2d7dad8cc2cad85
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2018
ms.locfileid: "53142707"
---
# <a name="how-to-determine-an-assembly39s-fully-qualified-name"></a><span data-ttu-id="66286-102">如何：确定程序集的完全限定的名称</span><span class="sxs-lookup"><span data-stu-id="66286-102">How to: Determine an Assembly&#39;s Fully Qualified Name</span></span>
<span data-ttu-id="66286-103">若要在全局程序集缓存中查找一个程序集的完全限定名，请使用全局程序集缓存工具 ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md))。</span><span class="sxs-lookup"><span data-stu-id="66286-103">To discover the fully qualified name of an assembly in the global assembly cache, use the Global Assembly Cache Tool ([Gacutil.exe](../../../docs/framework/tools/gacutil-exe-gac-tool.md)).</span></span> <span data-ttu-id="66286-104">请参阅[如何：查看全局程序集缓存的内容](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md)。</span><span class="sxs-lookup"><span data-stu-id="66286-104">See [How to: View the Contents of the Global Assembly Cache](../../../docs/framework/app-domains/how-to-view-the-contents-of-the-gac.md).</span></span>  
  
 <span data-ttu-id="66286-105">对于不在全局程序集缓存中的程序集，可以通过多种方式获取完全限定的程序集名称：可使用代码将信息输出到控制台或变量，也可使用 [Ildasm.exe（IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)检查包含完全限定名的程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="66286-105">For assemblies that are not in the global assembly cache, you can get the fully qualified assembly name in a number of ways: can use code to output the information to the console or to a variable, or you can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
-   <span data-ttu-id="66286-106">如果应用程序已加载程序集，则可检索 <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> 属性的值在以获取完全限定名。</span><span class="sxs-lookup"><span data-stu-id="66286-106">If the assembly is already loaded by the application, you can retrieve the value of the <xref:System.Reflection.Assembly.FullName%2A?displayProperty=nameWithType> property to get the fully qualified name.</span></span> <span data-ttu-id="66286-107">无论 GAC 是否包含程序集，均可使用此方法。</span><span class="sxs-lookup"><span data-stu-id="66286-107">You can use this approach whether or not the assembly is in the GAC.</span></span> <span data-ttu-id="66286-108">说明如示例所示。</span><span class="sxs-lookup"><span data-stu-id="66286-108">The example provides an illustration.</span></span>  
  
-   <span data-ttu-id="66286-109">如果知道程序集的文件系统路径，则可调用静态（Visual Basic 中的 `Shared`）<xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> 方法获取完全限定的程序集名称。</span><span class="sxs-lookup"><span data-stu-id="66286-109">If you know the assembly's file system path, you can call the static (`Shared` in Visual Basic) <xref:System.Reflection.AssemblyName.GetAssemblyName%2A?displayProperty=nameWithType> method to get the fully qualified assembly name.</span></span> <span data-ttu-id="66286-110">下面是一个简单的示例。</span><span class="sxs-lookup"><span data-stu-id="66286-110">The following is a simple example.</span></span>  
  
     [!code-csharp[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/cs/getassemblyname1.cs#1)]
     [!code-vb[System.Reflection.AssemblyName.GetAssemblyName#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.reflection.assemblyname.getassemblyname/vb/getassemblyname1.vb#1)]  
  
-   <span data-ttu-id="66286-111">可使用 [Ildasm.exe（IL 反汇编程序）](../../../docs/framework/tools/ildasm-exe-il-disassembler.md)检查包含完全限定名的程序集元数据。</span><span class="sxs-lookup"><span data-stu-id="66286-111">You can use the [Ildasm.exe (IL Disassembler)](../../../docs/framework/tools/ildasm-exe-il-disassembler.md) to examine the assembly's metadata, which contains the fully qualified name.</span></span>  
  
 <span data-ttu-id="66286-112">有关设置程序集特性（如版本、区域性和程序集名称）的详细信息，请参阅[设置程序集特性](../../../docs/framework/app-domains/set-assembly-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="66286-112">For more information about setting assembly attributes such as version, culture, and assembly name, see [Setting Assembly Attributes](../../../docs/framework/app-domains/set-assembly-attributes.md).</span></span> <span data-ttu-id="66286-113">有关为程序集提供强名称的详细信息，请参阅[创建并使用强名称程序集](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)。</span><span class="sxs-lookup"><span data-stu-id="66286-113">For more information about giving an assembly a strong name, see [Creating and Using Strong-Named Assemblies](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="66286-114">示例</span><span class="sxs-lookup"><span data-stu-id="66286-114">Example</span></span>  
 <span data-ttu-id="66286-115">以下代码示例显示了如何向控制台显示包含指定类的程序集的完全限定名。</span><span class="sxs-lookup"><span data-stu-id="66286-115">The following code example shows how to display the fully qualified name of an assembly containing a specified class to the console.</span></span> <span data-ttu-id="66286-116">因为它检索应用程序已加载的程序集的名称，所以程序集是否位于 GAC 中并不重要。</span><span class="sxs-lookup"><span data-stu-id="66286-116">Because it retrieves the name of an assembly that the app has already loaded, it does not matter whether the assembly is in the GAC.</span></span>  
  
 [!code-cpp[Assembly.Fullname#2](../../../samples/snippets/cpp/VS_Snippets_CLR/Assembly.FullName/CPP/example2.cpp#2)]
 [!code-csharp[Assembly.Fullname#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Assembly.FullName/CS/example2.cs#2)]
 [!code-vb[Assembly.Fullname#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Assembly.FullName/VB/example2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="66286-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="66286-117">See Also</span></span>  
- [<span data-ttu-id="66286-118">程序集名称</span><span class="sxs-lookup"><span data-stu-id="66286-118">Assembly Names</span></span>](../../../docs/framework/app-domains/assembly-names.md)  
- [<span data-ttu-id="66286-119">创建程序集</span><span class="sxs-lookup"><span data-stu-id="66286-119">Creating Assemblies</span></span>](../../../docs/framework/app-domains/create-assemblies.md)  
- [<span data-ttu-id="66286-120">创建和使用具有强名称的程序集</span><span class="sxs-lookup"><span data-stu-id="66286-120">Creating and Using Strong-Named Assemblies</span></span>](../../../docs/framework/app-domains/create-and-use-strong-named-assemblies.md)  
- [<span data-ttu-id="66286-121">全局程序集缓存</span><span class="sxs-lookup"><span data-stu-id="66286-121">Global Assembly Cache</span></span>](../../../docs/framework/app-domains/gac.md)  
- [<span data-ttu-id="66286-122">运行时如何定位程序集</span><span class="sxs-lookup"><span data-stu-id="66286-122">How the Runtime Locates Assemblies</span></span>](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)  
- [<span data-ttu-id="66286-123">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="66286-123">Programming with Assemblies</span></span>](../../../docs/framework/app-domains/programming-with-assemblies.md)
