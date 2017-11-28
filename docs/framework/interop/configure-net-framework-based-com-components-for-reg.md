---
title: "如何：配置基于 .NET Framework 的 COM 组件以进行免注册激活"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- components [.NET Framework], manifest
- application manifests [.NET Framework]
- manifests [.NET Framework]
- registration-free COM interop, configuring .NET-based components
- activation, registration-free
ms.assetid: 32f8b7c6-3f73-455d-8e13-9846895bd43b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d373d6abc82e482a3b1df873295573f0e34eeda2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-configure-net-framework-based-com-components-for-registration-free-activation"></a><span data-ttu-id="b9a95-102">如何：配置基于 .NET Framework 的 COM 组件以进行免注册激活</span><span class="sxs-lookup"><span data-stu-id="b9a95-102">How to: Configure .NET Framework-Based COM Components for Registration-Free Activation</span></span>
<span data-ttu-id="b9a95-103">基于 .NET Framework 的组件的免注册激活略复杂于 COM 组件的免注册激活。</span><span class="sxs-lookup"><span data-stu-id="b9a95-103">Registration-free activation for .NET Framework-based components is only slightly more complicated than it is for COM components.</span></span> <span data-ttu-id="b9a95-104">安装需要两个清单：</span><span class="sxs-lookup"><span data-stu-id="b9a95-104">The setup requires two manifests:</span></span>  
  
-   <span data-ttu-id="b9a95-105">COM 应用程序必须具有 Win32 样式的应用程序清单，以标识托管的组件。</span><span class="sxs-lookup"><span data-stu-id="b9a95-105">COM applications must have a Win32-style application manifest to identify the managed component.</span></span>  
  
-   <span data-ttu-id="b9a95-106">基于 .NET Framework 的组件必须具有组件清单，以提供运行时所需的激活信息。</span><span class="sxs-lookup"><span data-stu-id="b9a95-106">.NET Framework-based components must have a component manifest for activation information needed at run time.</span></span>  
  
 <span data-ttu-id="b9a95-107">本主题将介绍如何应用程序清单与应用程序关联，如何将组件清单与组件关联，以及如何在程序集中嵌入组件清单。</span><span class="sxs-lookup"><span data-stu-id="b9a95-107">This topic describes how to associate an application manifest with an application; associate a component manifest with a component; and embed a component manifest in an assembly.</span></span>  
  
### <a name="to-create-an-application-manifest"></a><span data-ttu-id="b9a95-108">创建应用程序清单</span><span class="sxs-lookup"><span data-stu-id="b9a95-108">To create an application manifest</span></span>  
  
1.  <span data-ttu-id="b9a95-109">使用 XML 编辑器创建（或修改）COM 应用程序拥有的应用程序清单，该应用程序与一个或多个托管组件进行交互操作。</span><span class="sxs-lookup"><span data-stu-id="b9a95-109">Using an XML editor, create (or modify) the application manifest owned by the COM application that is interoperating with one or more managed components.</span></span>  
  
2.  <span data-ttu-id="b9a95-110">在文件开头插入以下标准标头：</span><span class="sxs-lookup"><span data-stu-id="b9a95-110">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
     <span data-ttu-id="b9a95-111">有关清单元素和其属性的信息，请参阅[应用程序清单](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b9a95-111">For information about manifest elements and their attributes, see [Application Manifests](https://msdn.microsoft.com/library/windows/desktop/aa374191.aspx).</span></span>  
  
3.  <span data-ttu-id="b9a95-112">标识清单的所有者。</span><span class="sxs-lookup"><span data-stu-id="b9a95-112">Identify the owner of the manifest.</span></span> <span data-ttu-id="b9a95-113">以下示例中，`myComApp` 版本 1 拥有清单文件。</span><span class="sxs-lookup"><span data-stu-id="b9a95-113">In the following example, `myComApp` version 1 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="msil"   
      />  
    ```  
  
4.  <span data-ttu-id="b9a95-114">标识依赖程序集。</span><span class="sxs-lookup"><span data-stu-id="b9a95-114">Identify dependent assemblies.</span></span> <span data-ttu-id="b9a95-115">以下示例中，`myComApp` 依赖于 `myManagedComp`。</span><span class="sxs-lookup"><span data-stu-id="b9a95-115">In the following example, `myComApp` depends on `myManagedComp`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
      <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myComApp"   
                        version="1.0.0.0"   
                        processorArchitecture="x86"   
                        publicKeyToken="8275b28176rcbbef"  
      />  
      <dependency>  
        <dependentAssembly>  
          <assemblyIdentity type="win32"   
                        name="myOrganization.myDivision.myManagedComp"   
                        version="6.0.0.0"   
                        processorArchitecture="X86"   
                        publicKeyToken="8275b28176rcbbef"  
          />  
        </dependentAssembly>  
      </dependency>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="b9a95-116">保存并命名清单文件。</span><span class="sxs-lookup"><span data-stu-id="b9a95-116">Save and name the manifest file.</span></span> <span data-ttu-id="b9a95-117">应用程序清单的名称是程序集可执行文件的名称后加 .manifest 扩展名。</span><span class="sxs-lookup"><span data-stu-id="b9a95-117">The name of an application manifest is the name of the assembly executable followed by the .manifest extension.</span></span> <span data-ttu-id="b9a95-118">例如，myComApp.exe 的应用程序清单文件名称是 myComApp.exe.manifest。</span><span class="sxs-lookup"><span data-stu-id="b9a95-118">For example, the application manifest file name for myComApp.exe is myComApp.exe.manifest.</span></span>  
  
 <span data-ttu-id="b9a95-119">可在与 COM 应用程序相同的目录中安装应用程序清单。</span><span class="sxs-lookup"><span data-stu-id="b9a95-119">You can install an application manifest in the same directory as the COM application.</span></span> <span data-ttu-id="b9a95-120">或者，可将其作为资源添加到应用程序的 .exe 文件。</span><span class="sxs-lookup"><span data-stu-id="b9a95-120">Alternatively, you can add it as a resource to the application's .exe file.</span></span> <span data-ttu-id="b9a95-121">有关其他信息，有关详细信息，请参阅[有关的并行程序集](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b9a95-121">For additional information, For more information, see [About Side-by-Side Assemblies](https://msdn.microsoft.com/library/windows/desktop/ff951640.aspx).</span></span>  
  
#### <a name="to-create-a-component-manifest"></a><span data-ttu-id="b9a95-122">创建组件清单</span><span class="sxs-lookup"><span data-stu-id="b9a95-122">To create a component manifest</span></span>  
  
1.  <span data-ttu-id="b9a95-123">使用 XML 编辑器创建组件清单，描述托管程序集。</span><span class="sxs-lookup"><span data-stu-id="b9a95-123">Using an XML editor, create a component manifest to describe the managed assembly.</span></span>  
  
2.  <span data-ttu-id="b9a95-124">在文件开头插入以下标准标头：</span><span class="sxs-lookup"><span data-stu-id="b9a95-124">Insert the following standard header at the beginning of the file:</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
    ```  
  
3.  <span data-ttu-id="b9a95-125">标识文件的所有者。</span><span class="sxs-lookup"><span data-stu-id="b9a95-125">Identify the owner of the file.</span></span> <span data-ttu-id="b9a95-126">应用程序清单文件中 `<dependentAssembly>` 元素的 `<assemblyIdentity>` 元素必须与组件清单中的该元素相匹配。</span><span class="sxs-lookup"><span data-stu-id="b9a95-126">The `<assemblyIdentity>` element of the `<dependentAssembly>` element in application manifest file must match the one in the component manifest.</span></span> <span data-ttu-id="b9a95-127">以下示例中，`myManagedComp` 版本 1.2.3.4 拥有清单文件。</span><span class="sxs-lookup"><span data-stu-id="b9a95-127">In the following example, `myManagedComp` version 1.2.3.4 owns the manifest file.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4"  
                        publicKeyToken="8275b28176rcbbef"  
                        processorArchitecture="msil"  
           />  
    ```  
  
4.  <span data-ttu-id="b9a95-128">标识程序集中的每个类。</span><span class="sxs-lookup"><span data-stu-id="b9a95-128">Identify each class in the assembly.</span></span> <span data-ttu-id="b9a95-129">使用 `<clrClass>` 元素来唯一地标识托管程序集中的每个类。</span><span class="sxs-lookup"><span data-stu-id="b9a95-129">Use the `<clrClass>` element to uniquely identify each class in the managed assembly.</span></span> <span data-ttu-id="b9a95-130">该元素是 `<assembly>` 元素的子元素，具有下表中描述的属性。</span><span class="sxs-lookup"><span data-stu-id="b9a95-130">The element, which is a subelement of the `<assembly>` element, has the attributes described in the following table.</span></span>  
  
    |<span data-ttu-id="b9a95-131">特性</span><span class="sxs-lookup"><span data-stu-id="b9a95-131">Attribute</span></span>|<span data-ttu-id="b9a95-132">描述</span><span class="sxs-lookup"><span data-stu-id="b9a95-132">Description</span></span>|<span data-ttu-id="b9a95-133">必需</span><span class="sxs-lookup"><span data-stu-id="b9a95-133">Required</span></span>|  
    |---------------|-----------------|--------------|  
    |`clsid`|<span data-ttu-id="b9a95-134">用于指定要激活的类的标识符。</span><span class="sxs-lookup"><span data-stu-id="b9a95-134">The identifier that specifies the class to be activated.</span></span>|<span data-ttu-id="b9a95-135">是</span><span class="sxs-lookup"><span data-stu-id="b9a95-135">Yes</span></span>|  
    |`description`|<span data-ttu-id="b9a95-136">用于通知用户组件相关信息的字符串。</span><span class="sxs-lookup"><span data-stu-id="b9a95-136">A string that informs the user about the component.</span></span> <span data-ttu-id="b9a95-137">空字符串为默认值。</span><span class="sxs-lookup"><span data-stu-id="b9a95-137">An empty string is the default.</span></span>|<span data-ttu-id="b9a95-138">No</span><span class="sxs-lookup"><span data-stu-id="b9a95-138">No</span></span>|  
    |`name`|<span data-ttu-id="b9a95-139">用于表示托管类的字符串。</span><span class="sxs-lookup"><span data-stu-id="b9a95-139">A string that represents the managed class.</span></span>|<span data-ttu-id="b9a95-140">是</span><span class="sxs-lookup"><span data-stu-id="b9a95-140">Yes</span></span>|  
    |`progid`|<span data-ttu-id="b9a95-141">用于后期绑定激活的标识符。</span><span class="sxs-lookup"><span data-stu-id="b9a95-141">The identifier to be used for late-bound activation.</span></span>|<span data-ttu-id="b9a95-142">No</span><span class="sxs-lookup"><span data-stu-id="b9a95-142">No</span></span>|  
    |`threadingModel`|<span data-ttu-id="b9a95-143">COM 线程模型。</span><span class="sxs-lookup"><span data-stu-id="b9a95-143">The COM threading model.</span></span> <span data-ttu-id="b9a95-144">“Both”为默认值。</span><span class="sxs-lookup"><span data-stu-id="b9a95-144">"Both" is the default value.</span></span>|<span data-ttu-id="b9a95-145">No</span><span class="sxs-lookup"><span data-stu-id="b9a95-145">No</span></span>|  
    |`runtimeVersion`|<span data-ttu-id="b9a95-146">指定要使用的公共语言运行时 (CLR) 版本。</span><span class="sxs-lookup"><span data-stu-id="b9a95-146">Specifies the common language runtime (CLR) version to use.</span></span> <span data-ttu-id="b9a95-147">如未指定此属性，并且尚未加载 CLR，将使用最近安装的早于 CLR 版本 4 的 CLR 版本加载组件。</span><span class="sxs-lookup"><span data-stu-id="b9a95-147">If you do not specify this attribute, and the CLR is not already loaded, the component is loaded with the latest installed CLR prior to CLR version 4.</span></span> <span data-ttu-id="b9a95-148">如果指定 v1.0.3705、v1.1.4322 或 v2.0.50727，版本将自动向前滚到最近安装的早于 CLR 版本 4 的 CLR 版本（通常为 v2.0.50727）。</span><span class="sxs-lookup"><span data-stu-id="b9a95-148">If you specify v1.0.3705, v1.1.4322, or v2.0.50727, the version automatically rolls forward to the latest installed CLR version prior to CLR version 4 (usually v2.0.50727).</span></span> <span data-ttu-id="b9a95-149">如果已加载其他 CLR 版本，并且可在进程内并行加载指定版本，那么将加载指定版本；否则使用已加载的 CLR。</span><span class="sxs-lookup"><span data-stu-id="b9a95-149">If another version of the CLR is already loaded and the specified version can be loaded side-by-side in-process, the specified version is loaded; otherwise, the loaded CLR is used.</span></span> <span data-ttu-id="b9a95-150">这可能会导致加载失败。</span><span class="sxs-lookup"><span data-stu-id="b9a95-150">This might cause a load failure.</span></span>|<span data-ttu-id="b9a95-151">No</span><span class="sxs-lookup"><span data-stu-id="b9a95-151">No</span></span>|  
    |`tlbid`|<span data-ttu-id="b9a95-152">包含有关该类的类型信息的类型库的标识符。</span><span class="sxs-lookup"><span data-stu-id="b9a95-152">The identifier of the type library that contains type information about the class.</span></span>|<span data-ttu-id="b9a95-153">No</span><span class="sxs-lookup"><span data-stu-id="b9a95-153">No</span></span>|  
  
     <span data-ttu-id="b9a95-154">所有属性标记都区分大小写。</span><span class="sxs-lookup"><span data-stu-id="b9a95-154">All attribute tags are case-sensitive.</span></span> <span data-ttu-id="b9a95-155">通过使用 OLE/COM ObjectViewer (Oleview.exe) 查看程序集的已导出类型库，可以获取 CLSID、ProgID、线程模型和运行时版本。</span><span class="sxs-lookup"><span data-stu-id="b9a95-155">You can obtain CLSIDs, ProgIDs, threading models, and the runtime version by viewing the exported type library for the assembly with the OLE/COM ObjectViewer (Oleview.exe).</span></span>  
  
     <span data-ttu-id="b9a95-156">以下组件清单标识两个类 - `testClass1` 和 `testClass2`。</span><span class="sxs-lookup"><span data-stu-id="b9a95-156">The following component manifest identifies two classes, `testClass1` and `testClass2`.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="UTF-8" standalone="yes"?>  
    <assembly xmlns="urn:schemas-microsoft-com:asm.v1" manifestVersion="1.0">  
           <assemblyIdentity  
                        name="myOrganization.myDivision.myManagedComp"  
                        version="1.2.3.4" />  
                        publicKeyToken="8275b28176rcbbef"  
           />  
           <clrClass  
                        clsid="{65722BE6-3449-4628-ABD3-74B6864F9739}"  
                        progid="myManagedComp.testClass1"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass1"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <clrClass  
                        clsid="{367221D6-3559-3328-ABD3-45B6825F9732}"  
                        progid="myManagedComp.testClass2"  
                        threadingModel="Both"  
                        name="myManagedComp.testClass2"  
                        runtimeVersion="v1.0.3705">  
           </clrClass>  
           <file name="MyManagedComp.dll">  
           </file>  
    </assembly>  
    ```  
  
5.  <span data-ttu-id="b9a95-157">保存并命名清单文件。</span><span class="sxs-lookup"><span data-stu-id="b9a95-157">Save and name the manifest file.</span></span> <span data-ttu-id="b9a95-158">组件清单名称是程序集库名称后加 .manifest 扩展名。</span><span class="sxs-lookup"><span data-stu-id="b9a95-158">The name of a component manifest is the name of the assembly library followed by the .manifest extension.</span></span> <span data-ttu-id="b9a95-159">例如，myManagedComp.dll 的名称是 myManagedComp.manifest。</span><span class="sxs-lookup"><span data-stu-id="b9a95-159">For example, the myManagedComp.dll is myManagedComp.manifest.</span></span>  
  
 <span data-ttu-id="b9a95-160">必须将组件清单作为资源嵌入程序集。</span><span class="sxs-lookup"><span data-stu-id="b9a95-160">You must embed the component manifest as a resource in the assembly.</span></span>  
  
#### <a name="to-embed-a-component-manifest-in-a-managed-assembly"></a><span data-ttu-id="b9a95-161">将组件清单嵌入托管程序集</span><span class="sxs-lookup"><span data-stu-id="b9a95-161">To embed a component manifest in a managed assembly</span></span>  
  
1.  <span data-ttu-id="b9a95-162">创建包含以下语句的资源脚本：</span><span class="sxs-lookup"><span data-stu-id="b9a95-162">Create a resource script that contains the following statement:</span></span>  
  
     `RT_MANIFEST 1 myManagedComp.manifest`  
  
     <span data-ttu-id="b9a95-163">在此语句中，`myManagedComp.manifest` 是正在嵌入的组件清单的名称。</span><span class="sxs-lookup"><span data-stu-id="b9a95-163">In this statement, `myManagedComp.manifest` is the name of the component manifest being embedded.</span></span> <span data-ttu-id="b9a95-164">对于此示例，脚本文件名称是 `myresource.rc`。</span><span class="sxs-lookup"><span data-stu-id="b9a95-164">For this example, the script file name is `myresource.rc`.</span></span>  
  
2.  <span data-ttu-id="b9a95-165">使用 Microsoft Windows 资源编译器 (rc.exe) 编译脚本。</span><span class="sxs-lookup"><span data-stu-id="b9a95-165">Compile the script using the Microsoft Windows Resource Compiler (Rc.exe).</span></span> <span data-ttu-id="b9a95-166">在命令提示符处，键入下列命令：</span><span class="sxs-lookup"><span data-stu-id="b9a95-166">At the command prompt, type the following command:</span></span>  
  
     `rc myresource.rc`  
  
     <span data-ttu-id="b9a95-167">Rc.exe 生成 `myresource.res` 资源文件。</span><span class="sxs-lookup"><span data-stu-id="b9a95-167">Rc.exe produces the `myresource.res` resource file.</span></span>  
  
3.  <span data-ttu-id="b9a95-168">再次编译该程序集的源文件，并使用 /win32res 选项指定资源文件：</span><span class="sxs-lookup"><span data-stu-id="b9a95-168">Compile the assembly's source file again and specify the resource file by using the **/win32res** option:</span></span>  
  
    ```  
    /win32res:myresource.res  
    ```  
  
     <span data-ttu-id="b9a95-169">同样，`myresource.res` 是包含嵌入资源的资源文件的名称。</span><span class="sxs-lookup"><span data-stu-id="b9a95-169">Again, `myresource.res` is the name of the resource file containing embedded resource.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9a95-170">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9a95-170">See Also</span></span>  
 [<span data-ttu-id="b9a95-171">免注册 COM 互操作</span><span class="sxs-lookup"><span data-stu-id="b9a95-171">Registration-Free COM Interop</span></span>](../../../docs/framework/interop/registration-free-com-interop.md)  
 [<span data-ttu-id="b9a95-172">免注册 COM 互操作的要求</span><span class="sxs-lookup"><span data-stu-id="b9a95-172">Requirements for Registration-Free COM Interop</span></span>](http://msdn.microsoft.com/en-us/0c43bc57-eecf-4e6c-8114-490141cce4da)  
 [<span data-ttu-id="b9a95-173">将 COM 组件配置为免注册激活</span><span class="sxs-lookup"><span data-stu-id="b9a95-173">Configuring COM Components for Registration-Free Activation</span></span>](http://msdn.microsoft.com/en-us/bfe9b02f-d964-4784-960e-a1f94692fbfe)  
 [<span data-ttu-id="b9a95-174">基于 .NET 组件的免注册激活：演练</span><span class="sxs-lookup"><span data-stu-id="b9a95-174">Registration-Free Activation of .NET-Based Components: A Walkthrough</span></span>](http://go.microsoft.com/fwlink/?LinkId=158812)
