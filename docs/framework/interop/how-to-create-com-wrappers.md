---
title: 如何：创建 COM 包装
ms.date: 03/30/2017
helpviewer_keywords:
- COM,wrappers creating
- COM,wrappers Visual Studio
ms.assetid: bdf89bea-1623-45ee-a57b-cf7c90395efa
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c4deb355a7b523437ae31a1d2b9c79e3b8d4f40a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-com-wrappers"></a><span data-ttu-id="92bc1-102">如何：创建 COM 包装</span><span class="sxs-lookup"><span data-stu-id="92bc1-102">How to: Create COM Wrappers</span></span>
<span data-ttu-id="92bc1-103">可以通过使用 [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] 功能或 .NET Framework 工具 Tlbimp.exe 和 Regasm.exe 创建组件对象模型 (COM) 包装器。</span><span class="sxs-lookup"><span data-stu-id="92bc1-103">You can create Component Object Model (COM) wrappers by using [!INCLUDE[vsprvsext](../../../includes/vsprvsext-md.md)] features or the .NET Framework tools Tlbimp.exe and Regasm.exe.</span></span> <span data-ttu-id="92bc1-104">这两种方法都会生成两种类型的 COM 包装器：</span><span class="sxs-lookup"><span data-stu-id="92bc1-104">Both methods generate two types of COM wrappers:</span></span>  
  
-   <span data-ttu-id="92bc1-105">从类型库中生成一个[运行时可调用包装器](../../../docs/framework/interop/runtime-callable-wrapper.md)以在托管代码中运行 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="92bc1-105">A [Runtime Callable Wrapper](../../../docs/framework/interop/runtime-callable-wrapper.md) from a type library to run a COM object in managed code.</span></span>  
  
-   <span data-ttu-id="92bc1-106">生成具有所需注册表设置的一个 [COM 可调用包装器](../../../docs/framework/interop/com-callable-wrapper.md)以在本机应用程序中运行托管对象。</span><span class="sxs-lookup"><span data-stu-id="92bc1-106">A [COM Callable Wrapper](../../../docs/framework/interop/com-callable-wrapper.md) with the required registry settings to run a managed object in a native application.</span></span>  
  
 <span data-ttu-id="92bc1-107">在 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 中，可以将 COM 包装器作为引用添加到项目中。</span><span class="sxs-lookup"><span data-stu-id="92bc1-107">In [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], you can add the COM wrapper as a reference to your project.</span></span>  
  
## <a name="wrapping-com-objects-in-a-managed-application"></a><span data-ttu-id="92bc1-108">在托管应用程序中包装 COM 对象</span><span class="sxs-lookup"><span data-stu-id="92bc1-108">Wrapping COM Objects in a Managed Application</span></span>  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-visual-studio"></a><span data-ttu-id="92bc1-109">使用 Visual Studio 创建运行时可调用包装器</span><span class="sxs-lookup"><span data-stu-id="92bc1-109">To create a runtime callable wrapper using Visual Studio</span></span>  
  
1.  <span data-ttu-id="92bc1-110">打开托管应用程序的项目。</span><span class="sxs-lookup"><span data-stu-id="92bc1-110">Open the project for your managed application.</span></span>  
  
2.  <span data-ttu-id="92bc1-111">在“项目”菜单上，单击“显示所有文件”。</span><span class="sxs-lookup"><span data-stu-id="92bc1-111">On the **Project** menu, click **Show All Files**.</span></span>  
  
3.  <span data-ttu-id="92bc1-112">在“项目”菜单上，单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="92bc1-112">On the **Project** menu, click **Add Reference**.</span></span>  
  
4.  <span data-ttu-id="92bc1-113">在“添加引用”对话框中，单击“COM”选项卡，选择要使用的组件，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="92bc1-113">In the Add Reference dialog box, click the **COM** tab, select the component you want to use, and click **OK**.</span></span>  
  
     <span data-ttu-id="92bc1-114">在“解决方案资源管理器”中检查 COM 组件是否已添加到项目的“引用”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="92bc1-114">In **Solution Explorer**, note that the COM component is added to the References folder in your project.</span></span>  
  
 <span data-ttu-id="92bc1-115">现在可以编写代码以访问 COM 对象。</span><span class="sxs-lookup"><span data-stu-id="92bc1-115">You can now write code to access the COM object.</span></span> <span data-ttu-id="92bc1-116">可以从通过声明对象开始，如使用适用于 [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] 的 `Imports` 语句或适用于 [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)] 的 `Using` 语句。</span><span class="sxs-lookup"><span data-stu-id="92bc1-116">You can begin by declaring the object, such as with an `Imports` statement for [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)] or a `Using` statement for [!INCLUDE[csprcslong](../../../includes/csprcslong-md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92bc1-117">如果要编写 Microsoft Office 组件的程序，请首先从 Microsoft 下载中心安装 [Microsoft Office 主互操作程序集](http://go.microsoft.com/fwlink/?LinkId=50479) (PIA)。</span><span class="sxs-lookup"><span data-stu-id="92bc1-117">If you want to program Microsoft Office components, first install the [Microsoft Office Primary Interop Assemblies](http://go.microsoft.com/fwlink/?LinkId=50479) (PIAs) from the Microsoft Download Center.</span></span> <span data-ttu-id="92bc1-118">在步骤 4 中，为所需的 Office 产品选择可用的最新版本的对象库，如 Microsoft Word 11.0 对象库。</span><span class="sxs-lookup"><span data-stu-id="92bc1-118">In step 4, select the latest version of the object library available for the Office product you want, such as the **Microsoft Word 11.0 Object Library**.</span></span>  
  
#### <a name="to-create-a-runtime-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="92bc1-119">使用 .NET Framework 工具创建运行时可调用包装器</span><span class="sxs-lookup"><span data-stu-id="92bc1-119">To create a runtime callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="92bc1-120">运行 [Tlbimp.exe（类型库导入程序）](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md)工具。</span><span class="sxs-lookup"><span data-stu-id="92bc1-120">Run the [Tlbimp.exe (Type Library Importer)](../../../docs/framework/tools/tlbimp-exe-type-library-importer.md) tool.</span></span>  
  
 <span data-ttu-id="92bc1-121">此工具为在原始类型库中定义的类型创建包含运行时元数据的程序集。</span><span class="sxs-lookup"><span data-stu-id="92bc1-121">This tool creates an assembly that contains run-time metadata for the types defined in the original type library.</span></span>  
  
## <a name="wrapping-managed-objects-in-a-native-application"></a><span data-ttu-id="92bc1-122">在本机应用程序中包装托管对象</span><span class="sxs-lookup"><span data-stu-id="92bc1-122">Wrapping Managed Objects in a Native Application</span></span>  
  
#### <a name="to-create-a-com-callable-wrapper-using-visual-studio"></a><span data-ttu-id="92bc1-123">使用 Visual Studio 创建 COM 可调用包装器</span><span class="sxs-lookup"><span data-stu-id="92bc1-123">To create a COM callable wrapper using Visual Studio</span></span>  
  
1.  <span data-ttu-id="92bc1-124">为要在本机代码中运行的托管类创建类库项目。</span><span class="sxs-lookup"><span data-stu-id="92bc1-124">Create a Class Library project for the managed class that you want to run in native code.</span></span> <span data-ttu-id="92bc1-125">此类必须具有默认的构造函数。</span><span class="sxs-lookup"><span data-stu-id="92bc1-125">The class must have a default constructor.</span></span>  
  
     <span data-ttu-id="92bc1-126">在 AssemblyInfo 文件中验证程序集是否具有由四部分构成的完整版本号。</span><span class="sxs-lookup"><span data-stu-id="92bc1-126">Verify that you have a complete four-part version number for your assembly in the AssemblyInfo file.</span></span> <span data-ttu-id="92bc1-127">在 Windows 注册表中维护版本控制需要此版本号。</span><span class="sxs-lookup"><span data-stu-id="92bc1-127">This number is required for maintaining versioning in the Windows registry.</span></span> <span data-ttu-id="92bc1-128">有关版本号的详细信息，请参阅[程序集版本控制](../../../docs/framework/app-domains/assembly-versioning.md)。</span><span class="sxs-lookup"><span data-stu-id="92bc1-128">For more information about version numbers, see [Assembly Versioning](../../../docs/framework/app-domains/assembly-versioning.md).</span></span>  
  
2.  <span data-ttu-id="92bc1-129">在“项目”菜单上，单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="92bc1-129">On the **Project** menu, click **Properties**.</span></span>  
  
3.  <span data-ttu-id="92bc1-130">单击“编译”选项卡。</span><span class="sxs-lookup"><span data-stu-id="92bc1-130">Click the **Compile** tab.</span></span>  
  
4.  <span data-ttu-id="92bc1-131">选择“为 COM 互操作注册”复选框。</span><span class="sxs-lookup"><span data-stu-id="92bc1-131">Select the **Register for COM interop** check box.</span></span>  
  
 <span data-ttu-id="92bc1-132">生成项目时，将自动为 COM 互操作注册程序集。</span><span class="sxs-lookup"><span data-stu-id="92bc1-132">When you build the project, the assembly is automatically registered for COM interop.</span></span> <span data-ttu-id="92bc1-133">如果要在 [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)] 中生成本机应用程序，可以通过单击“项目”菜单上的“添加引用”来使用此程序集。</span><span class="sxs-lookup"><span data-stu-id="92bc1-133">If you are building a native application in [!INCLUDE[vsprvslong](../../../includes/vsprvslong-md.md)], you can use the assembly by clicking **Add Reference** on the **Project** menu.</span></span>  
  
#### <a name="to-create-a-com-callable-wrapper-using-net-framework-tools"></a><span data-ttu-id="92bc1-134">使用 .NET Framework 工具创建 COM 可调用包装器</span><span class="sxs-lookup"><span data-stu-id="92bc1-134">To create a COM callable wrapper using .NET Framework tools</span></span>  
  
-   <span data-ttu-id="92bc1-135">运行 [Regasm.exe（程序集注册工具）](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md)工具。</span><span class="sxs-lookup"><span data-stu-id="92bc1-135">Run the [Regasm.exe (Assembly Registration Tool)](../../../docs/framework/tools/regasm-exe-assembly-registration-tool.md) tool.</span></span>  
  
 <span data-ttu-id="92bc1-136">此工具读取程序集元数据，并向注册表添加所需的项。</span><span class="sxs-lookup"><span data-stu-id="92bc1-136">This tool reads the assembly metadata and adds the necessary entries to the registry.</span></span> <span data-ttu-id="92bc1-137">这样，使 COM 客户端可以透明方式创建 .NET Framework 类。</span><span class="sxs-lookup"><span data-stu-id="92bc1-137">As a result, COM clients can create .NET Framework classes transparently.</span></span> <span data-ttu-id="92bc1-138">可以像使用本机 COM 类一样可以使用此程序集。</span><span class="sxs-lookup"><span data-stu-id="92bc1-138">You can use the assembly as if it were a native COM class.</span></span>  
  
 <span data-ttu-id="92bc1-139">可以在任何目录中的程序集上运行 Regasm.exe，然后运行 [Gacutil.exe（全局程序集缓存工具）](../../../docs/framework/tools/gacutil-exe-gac-tool.md)以将其移动到全局程序集缓存中。</span><span class="sxs-lookup"><span data-stu-id="92bc1-139">You can run Regasm.exe on an assembly located in any directory, and then run the [Gacutil.exe (Global Assembly Cache Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md) to move it to the global assembly cache.</span></span> <span data-ttu-id="92bc1-140">移动此程序集不会使位置注册表项失效，因为如果未在其他位置找到此程序集，则会始终对全局程序集缓存进行检查。</span><span class="sxs-lookup"><span data-stu-id="92bc1-140">Moving the assembly does not invalidate location registry entries, because the global assembly cache is always examined if the assembly is not found elsewhere.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92bc1-141">请参阅</span><span class="sxs-lookup"><span data-stu-id="92bc1-141">See Also</span></span>  
 [<span data-ttu-id="92bc1-142">运行时可调用包装器</span><span class="sxs-lookup"><span data-stu-id="92bc1-142">Runtime Callable Wrapper</span></span>](../../../docs/framework/interop/runtime-callable-wrapper.md)  
 [<span data-ttu-id="92bc1-143">COM 可调用包装器</span><span class="sxs-lookup"><span data-stu-id="92bc1-143">COM Callable Wrapper</span></span>](../../../docs/framework/interop/com-callable-wrapper.md)
