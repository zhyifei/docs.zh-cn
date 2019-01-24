---
title: 演练：创建在 WPF 中承载的 Direct3D9 内容
ms.date: 03/30/2017
dev_langs:
- cpp
helpviewer_keywords:
- WPF [WPF], creating Direct3D9 content
- Direct3D9 [WPF interoperability], creating Direct3D9 content
ms.assetid: 286e98bc-1eaa-4b5e-923d-3490a9cca5fc
ms.openlocfilehash: 8e598b557381bf82b42ea87e2f020ebba4450929
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54520290"
---
# <a name="walkthrough-creating-direct3d9-content-for-hosting-in-wpf"></a><span data-ttu-id="69e31-102">演练：创建在 WPF 中承载的 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="69e31-102">Walkthrough: Creating Direct3D9 Content for Hosting in WPF</span></span>
<span data-ttu-id="69e31-103">本演练演示如何创建适用于 Windows Presentation Foundation (WPF) 应用程序中承载的 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="69e31-103">This walkthrough shows how to create Direct3D9 content that is suitable for hosting in a Windows Presentation Foundation (WPF) application.</span></span> <span data-ttu-id="69e31-104">承载 WPF 应用程序中的 Direct3D9 内容的详细信息，请参阅[WPF 和 Direct3D9 互操作](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md)。</span><span class="sxs-lookup"><span data-stu-id="69e31-104">For more information on hosting Direct3D9 content in WPF applications, see [WPF and Direct3D9 Interoperation](../../../../docs/framework/wpf/advanced/wpf-and-direct3d9-interoperation.md).</span></span>

 <span data-ttu-id="69e31-105">在本演练中，你将要执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="69e31-105">In this walkthrough, you perform the following tasks:</span></span>

-   <span data-ttu-id="69e31-106">创建 Direct3D9 项目。</span><span class="sxs-lookup"><span data-stu-id="69e31-106">Create a Direct3D9 project.</span></span>

-   <span data-ttu-id="69e31-107">配置用于 WPF 应用程序中承载的 Direct3D9 项目。</span><span class="sxs-lookup"><span data-stu-id="69e31-107">Configure the Direct3D9 project for hosting in a WPF application.</span></span>

 <span data-ttu-id="69e31-108">完成，你将拥有一个 DLL，它包含在 WPF 应用程序中使用的 Direct3D9 内容。</span><span class="sxs-lookup"><span data-stu-id="69e31-108">When you are finished, you will have a DLL that contains Direct3D9 content for use in a WPF application.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="69e31-109">系统必备</span><span class="sxs-lookup"><span data-stu-id="69e31-109">Prerequisites</span></span>
 <span data-ttu-id="69e31-110">你需要以下组件来完成本演练：</span><span class="sxs-lookup"><span data-stu-id="69e31-110">You need the following components to complete this walkthrough:</span></span>

-   <span data-ttu-id="69e31-111">Visual Studio 2010。</span><span class="sxs-lookup"><span data-stu-id="69e31-111">Visual Studio 2010.</span></span>

-   <span data-ttu-id="69e31-112">DirectX 9 或更高版本的 SDK。</span><span class="sxs-lookup"><span data-stu-id="69e31-112">DirectX SDK 9 or later.</span></span>

## <a name="creating-the-direct3d9-project"></a><span data-ttu-id="69e31-113">创建 Direct3D9 项目</span><span class="sxs-lookup"><span data-stu-id="69e31-113">Creating the Direct3D9 Project</span></span>
 <span data-ttu-id="69e31-114">第一步是创建和配置 Direct3D9 项目。</span><span class="sxs-lookup"><span data-stu-id="69e31-114">The first step is to create and configure the Direct3D9 project.</span></span>

#### <a name="to-create-the-direct3d9-project"></a><span data-ttu-id="69e31-115">若要创建 Direct3D9 项目</span><span class="sxs-lookup"><span data-stu-id="69e31-115">To create the Direct3D9 project</span></span>

1.  <span data-ttu-id="69e31-116">在名为 c + + 中创建新的 Win32 项目`D3DContent`。</span><span class="sxs-lookup"><span data-stu-id="69e31-116">Create a new Win32 Project in C++ named `D3DContent`.</span></span>

     <span data-ttu-id="69e31-117">Win32 应用程序向导将打开并显示欢迎屏幕。</span><span class="sxs-lookup"><span data-stu-id="69e31-117">The Win32 Application Wizard opens and displays the Welcome screen.</span></span>

2.  <span data-ttu-id="69e31-118">单击 **“下一步”**。</span><span class="sxs-lookup"><span data-stu-id="69e31-118">Click **Next**.</span></span>

     <span data-ttu-id="69e31-119">应用程序设置屏幕会显示。</span><span class="sxs-lookup"><span data-stu-id="69e31-119">The Application Settings screen appears.</span></span>

3.  <span data-ttu-id="69e31-120">在中**应用程序类型：** 部分中，选择**DLL**选项。</span><span class="sxs-lookup"><span data-stu-id="69e31-120">In the **Application type:** section, select the **DLL** option.</span></span>

4.  <span data-ttu-id="69e31-121">单击 **“完成”**。</span><span class="sxs-lookup"><span data-stu-id="69e31-121">Click **Finish**.</span></span>

     <span data-ttu-id="69e31-122">将生成 D3DContent 项目。</span><span class="sxs-lookup"><span data-stu-id="69e31-122">The D3DContent project is generated.</span></span>

5.  <span data-ttu-id="69e31-123">在解决方案资源管理器，右键单击 D3DContent 项目并选择**属性**。</span><span class="sxs-lookup"><span data-stu-id="69e31-123">In Solution Explorer, right-click the D3DContent project and select **Properties**.</span></span>

     <span data-ttu-id="69e31-124">**D3DContent 属性页**对话框随即打开。</span><span class="sxs-lookup"><span data-stu-id="69e31-124">The **D3DContent Property Pages** dialog box opens.</span></span>

6.  <span data-ttu-id="69e31-125">选择**C/c + +** 节点。</span><span class="sxs-lookup"><span data-stu-id="69e31-125">Select the **C/C++** node.</span></span>

7.  <span data-ttu-id="69e31-126">在中**附加包含目录**字段中，指定的 DirectX 的位置包括文件夹。</span><span class="sxs-lookup"><span data-stu-id="69e31-126">In the **Additional Include Directories** field, specify the location of the DirectX include folder.</span></span> <span data-ttu-id="69e31-127">此文件夹的默认位置为 %ProgramFiles%\Microsoft DirectX SDK (*版本*) \Include。</span><span class="sxs-lookup"><span data-stu-id="69e31-127">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Include.</span></span>

8.  <span data-ttu-id="69e31-128">双击**链接器**节点以将其展开。</span><span class="sxs-lookup"><span data-stu-id="69e31-128">Double-click the **Linker** node to expand it.</span></span>

9. <span data-ttu-id="69e31-129">在中**附加库目录**字段中，指定 DirectX 库文件夹的位置。</span><span class="sxs-lookup"><span data-stu-id="69e31-129">In the **Additional Library Directories** field, specify the location of the DirectX libraries folder.</span></span> <span data-ttu-id="69e31-130">此文件夹的默认位置为 %ProgramFiles%\Microsoft DirectX SDK (*版本*) \Lib\x86。</span><span class="sxs-lookup"><span data-stu-id="69e31-130">The default location for this folder is %ProgramFiles%\Microsoft DirectX SDK (*version*)\Lib\x86.</span></span>

10. <span data-ttu-id="69e31-131">选择**输入**节点。</span><span class="sxs-lookup"><span data-stu-id="69e31-131">Select the **Input** node.</span></span>

11. <span data-ttu-id="69e31-132">在中**附加依赖项**字段中，添加`d3d9.lib`和`d3dx9.lib`文件。</span><span class="sxs-lookup"><span data-stu-id="69e31-132">In the **Additional Dependencies** field, add the `d3d9.lib` and `d3dx9.lib` files.</span></span>

12. <span data-ttu-id="69e31-133">在解决方案资源管理器，添加新模块定义文件 (.def) 名为`D3DContent.def`到项目。</span><span class="sxs-lookup"><span data-stu-id="69e31-133">In Solution Explorer, add a new module definition file (.def) named `D3DContent.def` to the project.</span></span>

## <a name="creating-the-direct3d9-content"></a><span data-ttu-id="69e31-134">创建 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="69e31-134">Creating the Direct3D9 Content</span></span>
 <span data-ttu-id="69e31-135">若要获得最佳性能，Direct3D9 内容必须使用特定的设置。</span><span class="sxs-lookup"><span data-stu-id="69e31-135">To get the best performance, your Direct3D9 content must use particular settings.</span></span> <span data-ttu-id="69e31-136">下面的代码演示如何创建具有最佳的性能特征的 Direct3D9 曲面。</span><span class="sxs-lookup"><span data-stu-id="69e31-136">The following code shows how to create a Direct3D9 surface that has the best performance characteristics.</span></span> <span data-ttu-id="69e31-137">有关详细信息，请参阅[Direct3D9 和 WPF 互操作性的性能注意事项](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)。</span><span class="sxs-lookup"><span data-stu-id="69e31-137">For more information, see [Performance Considerations for Direct3D9 and WPF Interoperability](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md).</span></span>

#### <a name="to-create-the-direct3d9-content"></a><span data-ttu-id="69e31-138">若要创建 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="69e31-138">To create the Direct3D9 content</span></span>

1.  <span data-ttu-id="69e31-139">使用解决方案资源管理器，将三个 c + + 类添加到名为以下的项目。</span><span class="sxs-lookup"><span data-stu-id="69e31-139">Using Solution Explorer, add three C++ classes to the project named the following.</span></span>

     <span data-ttu-id="69e31-140">`CRenderer` （具有虚拟析构函数）</span><span class="sxs-lookup"><span data-stu-id="69e31-140">`CRenderer` (with virtual destructor)</span></span>

     `CRendererManager`

     `CTriangleRenderer`

2.  <span data-ttu-id="69e31-141">在代码编辑器中打开 Renderer.h 并自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-141">Open Renderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.h#rendererh)]

3.  <span data-ttu-id="69e31-142">在代码编辑器中打开 Renderer.cpp 并自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-142">Open Renderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderer.cpp#renderercpp)]

4.  <span data-ttu-id="69e31-143">在代码编辑器中打开 RendererManager.h 并自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-143">Open RendererManager.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.h#renderermanagerh)]

5.  <span data-ttu-id="69e31-144">在代码编辑器中打开 RendererManager.cpp 并自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-144">Open RendererManager.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#RendererManagerCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/renderermanager.cpp#renderermanagercpp)]

6.  <span data-ttu-id="69e31-145">在代码编辑器中打开 TriangleRenderer.h 并自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-145">Open TriangleRenderer.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.h#trianglerendererh)]

7.  <span data-ttu-id="69e31-146">在代码编辑器中打开 TriangleRenderer.cpp 并自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-146">Open TriangleRenderer.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#TriangleRendererCPP](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/trianglerenderer.cpp#trianglerenderercpp)]

8.  <span data-ttu-id="69e31-147">在代码编辑器中打开 stdafx.h 和自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-147">Open stdafx.h in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#StdafxH](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/stdafx.h#stdafxh)]

9. <span data-ttu-id="69e31-148">在代码编辑器中打开 dllmain.cpp 并自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-148">Open dllmain.cpp in the Code Editor and replace the automatically generated code with the following code.</span></span>

     [!code-cpp[System.Windows.Interop.D3DImage#DllMain](../../../../samples/snippets/cpp/VS_Snippets_Wpf/System.Windows.Interop.D3DImage/cpp/dllmain.cpp#dllmain)]

10. <span data-ttu-id="69e31-149">在代码编辑器中打开 D3DContent.def。</span><span class="sxs-lookup"><span data-stu-id="69e31-149">Open D3DContent.def in the code editor.</span></span>

11. <span data-ttu-id="69e31-150">自动生成的代码替换为以下代码。</span><span class="sxs-lookup"><span data-stu-id="69e31-150">Replace the automatically generated code with the following code.</span></span>

    ```
    LIBRARY "D3DContent"

    EXPORTS

    SetSize
    SetAlpha
    SetNumDesiredSamples
    SetAdapter

    GetBackBufferNoRef
    Render
    Destroy
    ```

12. <span data-ttu-id="69e31-151">生成项目。</span><span class="sxs-lookup"><span data-stu-id="69e31-151">Build the project.</span></span>

## <a name="next-steps"></a><span data-ttu-id="69e31-152">后续步骤</span><span class="sxs-lookup"><span data-stu-id="69e31-152">Next Steps</span></span>

-   <span data-ttu-id="69e31-153">承载 Direct3D9 内容在 WPF 应用程序。</span><span class="sxs-lookup"><span data-stu-id="69e31-153">Host the Direct3D9 content in a WPF application.</span></span> <span data-ttu-id="69e31-154">有关详细信息，请参见[演练：承载 Direct3D9 内容在 WPF 中的](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)。</span><span class="sxs-lookup"><span data-stu-id="69e31-154">For more information, see [Walkthrough: Hosting Direct3D9 Content in WPF](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="69e31-155">请参阅</span><span class="sxs-lookup"><span data-stu-id="69e31-155">See also</span></span>

- <xref:System.Windows.Interop.D3DImage>
- [<span data-ttu-id="69e31-156">Direct3D9 和 WPF 互操作性的性能注意事项</span><span class="sxs-lookup"><span data-stu-id="69e31-156">Performance Considerations for Direct3D9 and WPF Interoperability</span></span>](../../../../docs/framework/wpf/advanced/performance-considerations-for-direct3d9-and-wpf-interoperability.md)
- [<span data-ttu-id="69e31-157">演练：在 WPF 中承载 Direct3D9 内容</span><span class="sxs-lookup"><span data-stu-id="69e31-157">Walkthrough: Hosting Direct3D9 Content in WPF</span></span>](../../../../docs/framework/wpf/advanced/walkthrough-hosting-direct3d9-content-in-wpf.md)
