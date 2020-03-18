---
title: 演练：在 Visual Studio 中嵌入托管程序集中的类型
ms.date: 08/19/2019
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
dev_langs:
- csharp
- vb
ms.openlocfilehash: f11fbedad766753ee462c5f597b823493cdaf7cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2020
ms.locfileid: "75338559"
---
# <a name="walkthrough-embed-types-from-managed-assemblies-in-visual-studio"></a><span data-ttu-id="c0764-102">演练：在 Visual Studio 中嵌入托管程序集中的类型</span><span class="sxs-lookup"><span data-stu-id="c0764-102">Walkthrough: Embed types from managed assemblies in Visual Studio</span></span>

<span data-ttu-id="c0764-103">如果嵌入强命名托管程序集中的类型信息，则可以对应用程序中的类型进行松耦合，以实现版本独立性。</span><span class="sxs-lookup"><span data-stu-id="c0764-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="c0764-104">也就是说，可以将程序编写为使用托管库任何版本中的类型，而不必对每个版本重新编译程序。</span><span class="sxs-lookup"><span data-stu-id="c0764-104">That is, your program can be written to use types from any version of a managed library without having to be recompiled for each new version.</span></span>

<span data-ttu-id="c0764-105">类型嵌入经常与 COM 互操作一起使用，例如使用 Microsoft Office 中的自动化对象的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c0764-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="c0764-106">通过嵌入类型信息，程序的同一个版本可以处理不同计算机上的不同 Microsoft Office 版本。</span><span class="sxs-lookup"><span data-stu-id="c0764-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="c0764-107">但也可以在完全托管的解决方案中使用类型嵌入。</span><span class="sxs-lookup"><span data-stu-id="c0764-107">However, you can also use type embedding with fully managed solutions.</span></span>

<span data-ttu-id="c0764-108">指定可嵌入的公共接口后，创建实现这些接口的运行时类。</span><span class="sxs-lookup"><span data-stu-id="c0764-108">After you specify the public interfaces that can be embedded, you create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="c0764-109">客户端程序可以通过引用包含这些公共接口的程序集，并将该引用的 `Embed Interop Types` 属性设置为 `True`，即可在设计时嵌入这些接口的类型信息。</span><span class="sxs-lookup"><span data-stu-id="c0764-109">A client program can embed the type information for the interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="c0764-110">然后，客户端程序可以加载类型化为这些接口的运行时对象的实例。</span><span class="sxs-lookup"><span data-stu-id="c0764-110">The client program can then load instances of the runtime objects typed as those interfaces.</span></span> <span data-ttu-id="c0764-111">这相当于使用命令行编译器和通过 [-link 编译器选项](../../csharp/language-reference/compiler-options/link-compiler-option.md)引用该程序集。</span><span class="sxs-lookup"><span data-stu-id="c0764-111">This is equivalent to using the command line compiler and referencing the assembly by using the [-link compiler option](../../csharp/language-reference/compiler-options/link-compiler-option.md).</span></span>

<span data-ttu-id="c0764-112">如果创建新版本的强命名运行时程序集，则不必重新编译客户端程序。</span><span class="sxs-lookup"><span data-stu-id="c0764-112">If you create a new version of your strong-named runtime assembly, the client program doesn't have to be recompiled.</span></span> <span data-ttu-id="c0764-113">客户端程序继续使用任何可用的运行时程序集版本，使用公共接口的嵌入类型信息。</span><span class="sxs-lookup"><span data-stu-id="c0764-113">The client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="c0764-114">在此演练中，将：</span><span class="sxs-lookup"><span data-stu-id="c0764-114">In this walkthrough, you:</span></span>

1. <span data-ttu-id="c0764-115">创建一个强命名程序集，使其中的公共接口包含可嵌入的类型信息。</span><span class="sxs-lookup"><span data-stu-id="c0764-115">Create a strong-named assembly with a public interface containing type information that can be embedded.</span></span>
1. <span data-ttu-id="c0764-116">创建一个实现公共接口的强命名运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="c0764-116">Create a strong-named runtime assembly that implements the public interface.</span></span>
1. <span data-ttu-id="c0764-117">创建一个客户端程序，该程序嵌入公共接口中的类型信息，并创建运行时程序集中的类的实例。</span><span class="sxs-lookup"><span data-stu-id="c0764-117">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>
1. <span data-ttu-id="c0764-118">修改并重新生成运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="c0764-118">Modify and rebuild the runtime assembly.</span></span>
1. <span data-ttu-id="c0764-119">运行客户端程序，查看是否使用运行时程序集的新版本，而不必进行重新编译。</span><span class="sxs-lookup"><span data-stu-id="c0764-119">Run the client program to see that it uses the new version of the runtime assembly without having to be recompiled.</span></span>

[!INCLUDE[note_settings_general](../../../includes/note-settings-general-md.md)]

## <a name="conditions-and-limitations"></a><span data-ttu-id="c0764-120">条件和限制</span><span class="sxs-lookup"><span data-stu-id="c0764-120">Conditions and limitations</span></span>

<span data-ttu-id="c0764-121">可以在以下条件下嵌入程序集中的类型信息：</span><span class="sxs-lookup"><span data-stu-id="c0764-121">You can embed type information from an assembly under the following conditions:</span></span>

- <span data-ttu-id="c0764-122">程序集至少公开一个公共接口。</span><span class="sxs-lookup"><span data-stu-id="c0764-122">The assembly exposes at least one public interface.</span></span>
- <span data-ttu-id="c0764-123">嵌入的接口使用具有唯一 GUID 的 `ComImport` 属性和 `Guid` 属性进行批注。</span><span class="sxs-lookup"><span data-stu-id="c0764-123">The embedded interfaces are annotated with `ComImport` attributes and `Guid` attributes with unique GUIDs.</span></span>
- <span data-ttu-id="c0764-124">程序集使用 `ImportedFromTypeLib` 特性或 `PrimaryInteropAssembly` 特性和程序集级别的 `Guid` 特性进行批注。</span><span class="sxs-lookup"><span data-stu-id="c0764-124">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="c0764-125">默认情况下，Visual C# 和 Visual Basic 项目模板包含程序集级别的 `Guid` 属性。</span><span class="sxs-lookup"><span data-stu-id="c0764-125">The Visual C# and Visual Basic project templates include an assembly-level `Guid` attribute by default.</span></span>

<span data-ttu-id="c0764-126">由于类型嵌入的主要功能是支持 COM 互操作程序集，因此在完全托管解决方案中嵌入类型信息时，将应用以下限制：</span><span class="sxs-lookup"><span data-stu-id="c0764-126">Because the primary function of type embedding is to support COM interop assemblies, the following limitations apply when you embed type information in a fully-managed solution:</span></span>

- <span data-ttu-id="c0764-127">仅嵌入特定于 COM 互操作的属性。</span><span class="sxs-lookup"><span data-stu-id="c0764-127">Only attributes specific to COM interop are embedded.</span></span> <span data-ttu-id="c0764-128">忽略其他属性。</span><span class="sxs-lookup"><span data-stu-id="c0764-128">Other attributes are ignored.</span></span>
- <span data-ttu-id="c0764-129">如果一个类型使用泛型参数，且泛型参数的类型是嵌入类型，则不能跨程序集边界使用该类型。</span><span class="sxs-lookup"><span data-stu-id="c0764-129">If a type uses generic parameters, and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="c0764-130">跨程序集边界的示例包括从另一个程序集调用方法或从另一个程序集中定义的类型派生类型。</span><span class="sxs-lookup"><span data-stu-id="c0764-130">Examples of crossing an assembly boundary include calling a method from another assembly or deriving a type from a type defined in another assembly.</span></span>
- <span data-ttu-id="c0764-131">不嵌入常量。</span><span class="sxs-lookup"><span data-stu-id="c0764-131">Constants are not embedded.</span></span>
- <span data-ttu-id="c0764-132"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> 类不支持将嵌入类型作为密钥。</span><span class="sxs-lookup"><span data-stu-id="c0764-132">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="c0764-133">可以实现自己的字典类型以支持将嵌入类型作为密钥。</span><span class="sxs-lookup"><span data-stu-id="c0764-133">You can implement your own dictionary type to support an embedded type as a key.</span></span>

## <a name="create-an-interface"></a><span data-ttu-id="c0764-134">创建接口</span><span class="sxs-lookup"><span data-stu-id="c0764-134">Create an interface</span></span>

<span data-ttu-id="c0764-135">第一步是创建类型等效性接口程序集。</span><span class="sxs-lookup"><span data-stu-id="c0764-135">The first step is to create the type equivalence interface assembly.</span></span>

1. <span data-ttu-id="c0764-136">在 Visual Studio 中，选择“文件” > “新建” > “项目”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-136">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="c0764-137">在“创建新项目”对话框中，在“搜索模板”框中键入“类库”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-137">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="c0764-138">从列表中选择 C# 或 Visual Basic“类库(.NET Framework)”模板，然后选择“下一步”   。</span><span class="sxs-lookup"><span data-stu-id="c0764-138">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="c0764-139">在“配置新项目”对话框的“项目名称”下，键入“TypeEquivalenceInterface”，然后选择“创建”     。</span><span class="sxs-lookup"><span data-stu-id="c0764-139">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceInterface*, and then select **Create**.</span></span> <span data-ttu-id="c0764-140">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="c0764-140">The new project is created.</span></span>

1. <span data-ttu-id="c0764-141">在“解决方案资源管理器”中，右键单击“Class1.cs”或“Class1.vb”文件，选择“重命名”，并将该文件从“Class1”重命名为“ISampleInterface”       。</span><span class="sxs-lookup"><span data-stu-id="c0764-141">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *ISampleInterface*.</span></span> <span data-ttu-id="c0764-142">出现提示时选择“是”，同时将类重命名为 `ISampleInterface`  。</span><span class="sxs-lookup"><span data-stu-id="c0764-142">Respond **Yes** to the prompt to also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="c0764-143">此类表示类的公共接口。</span><span class="sxs-lookup"><span data-stu-id="c0764-143">This class represents the public interface for the class.</span></span>

1. <span data-ttu-id="c0764-144">在“解决方案资源管理器”中，右键单击 TypeEquivalenceInterface 项目，然后选择“属性”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-144">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project, and then select **Properties**.</span></span>

1. <span data-ttu-id="c0764-145">在“属性”屏幕的左窗格中选择“生成”，并将“输出路径”设置为计算机上的某个位置（例如 C:\TypeEquivalenceSample）     。</span><span class="sxs-lookup"><span data-stu-id="c0764-145">Select **Build** on the left pane of the **Properties** screen, and set the **Output path** to a location on your computer, such as *C:\TypeEquivalenceSample*.</span></span> <span data-ttu-id="c0764-146">本演练中使用相同的位置。</span><span class="sxs-lookup"><span data-stu-id="c0764-146">You use the same location throughout this walkthrough.</span></span>

1. <span data-ttu-id="c0764-147">在“属性”屏幕的左窗格中选择“签名”，然后选择“对程序集签名”复选框    。</span><span class="sxs-lookup"><span data-stu-id="c0764-147">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="c0764-148">在“选择强名称密钥文件”下拉列表中，选择“新建”   。</span><span class="sxs-lookup"><span data-stu-id="c0764-148">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="c0764-149">在“创建强名称密钥”对话框的“密钥文件名称”下，键入“key.snk”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-149">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="c0764-150">取消选中“使用密码保护密钥文件”复选框，然后选择“确定”   。</span><span class="sxs-lookup"><span data-stu-id="c0764-150">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="c0764-151">在代码编辑器中打开 ISampleInterface 类文件，将其内容替换为以下代码，以便创建 `ISampleInterface` 接口  ：</span><span class="sxs-lookup"><span data-stu-id="c0764-151">Open the *ISampleInterface* class file in the code editor, and replace its contents with the following code to create the `ISampleInterface` interface:</span></span>

   ```csharp
   using System;
   using System.Runtime.InteropServices;

   namespace TypeEquivalenceInterface
   {
       [ComImport]
       [Guid("8DA56996-A151-4136-B474-32784559F6DF")]
       public interface ISampleInterface
       {
           void GetUserInput();
           string UserInput { get; }
       }
   }
   ```

   ```vb
   Imports System.Runtime.InteropServices

   <ComImport()>
   <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
   Public Interface ISampleInterface
       Sub GetUserInput()
       ReadOnly Property UserInput As String
   End Interface
   ```

1. <span data-ttu-id="c0764-152">在“工具”菜单上，选择“创建 GUID”，然后在“创建 GUID”对话框中，选择“注册表格式”     。</span><span class="sxs-lookup"><span data-stu-id="c0764-152">On the **Tools** menu, select **Create Guid**, and in the **Create GUID** dialog box, select **Registry Format**.</span></span> <span data-ttu-id="c0764-153">选择“复制”，然后选择“退出”   。</span><span class="sxs-lookup"><span data-stu-id="c0764-153">Select **Copy**, and then select **Exit**.</span></span>

1. <span data-ttu-id="c0764-154">在代码的 `Guid` 属性中，将示例 GUID 替换为复制的 GUID，并删除大括号 ({ })  。</span><span class="sxs-lookup"><span data-stu-id="c0764-154">In the `Guid` attribute of your code, replace the sample GUID with the GUID you copied, and remove the braces (**{ }**).</span></span>

1. <span data-ttu-id="c0764-155">在“解决方案资源管理器”中，展开“属性”文件夹，并选择“AssemblyInfo.cs”或“AssemblyInfo.vb”文件     。</span><span class="sxs-lookup"><span data-stu-id="c0764-155">In **Solution Explorer**, expand the **Properties** folder and select the *AssemblyInfo.cs* or *AssemblyInfo.vb* file.</span></span> <span data-ttu-id="c0764-156">在代码编辑器中，将以下属性添加到文件：</span><span class="sxs-lookup"><span data-stu-id="c0764-156">In the code editor, add the following attribute to the file:</span></span>

   ```csharp
   [assembly: ImportedFromTypeLib("")]
   ```

   ```vb
   <Assembly: ImportedFromTypeLib("")>
   ```

1. <span data-ttu-id="c0764-157">选择“文件” > “保存全部”，或按 Ctrl+Shift+S 来保存文件和项目      。</span><span class="sxs-lookup"><span data-stu-id="c0764-157">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="c0764-158">在“解决方案资源管理器”中，右键单击 TypeEquivalenceInterface 项目，然后选择“生成”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-158">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="c0764-159">编译类库 DLL 文件，并保存到指定的生成输出路径中（如 C:\TypeEquivalenceSample）  。</span><span class="sxs-lookup"><span data-stu-id="c0764-159">The class library DLL file is compiled and saved to the specified build output path, for example *C:\TypeEquivalenceSample*.</span></span>

## <a name="create-a-runtime-class"></a><span data-ttu-id="c0764-160">创建运行时类</span><span class="sxs-lookup"><span data-stu-id="c0764-160">Create a runtime class</span></span>

<span data-ttu-id="c0764-161">接下来，创建类型等效性运行时类。</span><span class="sxs-lookup"><span data-stu-id="c0764-161">Next, create the type equivalence runtime class.</span></span>

1. <span data-ttu-id="c0764-162">在 Visual Studio 中，选择“文件” > “新建” > “项目”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-162">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="c0764-163">在“创建新项目”对话框中，在“搜索模板”框中键入“类库”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-163">In the **Create a new project** dialog box, type *class library* in the **Search for templates** box.</span></span> <span data-ttu-id="c0764-164">从列表中选择 C# 或 Visual Basic“类库(.NET Framework)”模板，然后选择“下一步”   。</span><span class="sxs-lookup"><span data-stu-id="c0764-164">Select either the C# or Visual Basic **Class Library (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="c0764-165">在“配置新项目”对话框的“项目名称”下，键入“TypeEquivalenceRuntime”，然后选择“创建”     。</span><span class="sxs-lookup"><span data-stu-id="c0764-165">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceRuntime*, and then select **Create**.</span></span> <span data-ttu-id="c0764-166">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="c0764-166">The new project is created.</span></span>

1. <span data-ttu-id="c0764-167">在“解决方案资源管理器”中，右键单击“Class1.cs”或“Class1.vb”文件，选择“重命名”，并将该文件从“Class1”重命名为“SampleClass”       。</span><span class="sxs-lookup"><span data-stu-id="c0764-167">In **Solution Explorer**, right-click the *Class1.cs* or *Class1.vb* file, select **Rename**, and rename the file from *Class1* to *SampleClass*.</span></span> <span data-ttu-id="c0764-168">出现提示时选择“是”，同时将类重命名为 `SampleClass`  。</span><span class="sxs-lookup"><span data-stu-id="c0764-168">Respond **Yes** to the prompt to also rename the class to `SampleClass`.</span></span> <span data-ttu-id="c0764-169">此类实现 `ISampleInterface` 接口。</span><span class="sxs-lookup"><span data-stu-id="c0764-169">This class implements the `ISampleInterface` interface.</span></span>

1. <span data-ttu-id="c0764-170">在“解决方案资源管理器”中，右键单击 TypeEquivalenceInterface 项目，并选择“属性”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-170">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="c0764-171">在“属性”屏幕的左窗格中选择“生成”，然后将“输出路径”设置为用于 TypeEquivalenceInterface 项目的同一位置（例如 C:\TypeEquivalenceSample）     。</span><span class="sxs-lookup"><span data-stu-id="c0764-171">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="c0764-172">在“属性”屏幕的左窗格中选择“签名”，然后选择“对程序集签名”复选框    。</span><span class="sxs-lookup"><span data-stu-id="c0764-172">Select **Signing** on the left pane of the **Properties** screen, and then select the **Sign the assembly** check box.</span></span> <span data-ttu-id="c0764-173">在“选择强名称密钥文件”下拉列表中，选择“新建”   。</span><span class="sxs-lookup"><span data-stu-id="c0764-173">In the dropdown for **Choose a strong name key file**, select **New**.</span></span>

1. <span data-ttu-id="c0764-174">在“创建强名称密钥”对话框的“密钥文件名称”下，键入“key.snk”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-174">In the **Create Strong Name Key** dialog, under **Key file name**, type *key.snk*.</span></span> <span data-ttu-id="c0764-175">取消选中“使用密码保护密钥文件”复选框，然后选择“确定”   。</span><span class="sxs-lookup"><span data-stu-id="c0764-175">Deselect the **Protect my key file with a password** check box, and then select **OK**.</span></span>

1. <span data-ttu-id="c0764-176">在“解决方案资源管理器”中，右键单击 TypeEquivalenceRuntime 项目，然后选择“添加” > “引用”     。</span><span class="sxs-lookup"><span data-stu-id="c0764-176">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="c0764-177">在“引用管理器”对话框中，选择“浏览”并浏览到输出路径文件夹   。</span><span class="sxs-lookup"><span data-stu-id="c0764-177">In the **Reference Manager** dialog, select **Browse** and browse to the output path folder.</span></span> <span data-ttu-id="c0764-178">选择 TypeEquivalenceInterface.dll 文件，选择“添加”，然后选择“确定”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-178">Select the *TypeEquivalenceInterface.dll* file, select **Add**, and then select **OK**.</span></span>

1. <span data-ttu-id="c0764-179">在“解决方案资源管理器”中，展开“引用”文件夹，并选择“TypeEquivalenceInterface”引用    。</span><span class="sxs-lookup"><span data-stu-id="c0764-179">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="c0764-180">在“属性”窗格中，将“特定版本”设置为“False”（如果尚未设置）    。</span><span class="sxs-lookup"><span data-stu-id="c0764-180">In the **Properties** pane, set **Specific Version** to **False** if it is not already.</span></span>

1. <span data-ttu-id="c0764-181">在代码编辑器中打开 SampleClass 类文件，将其内容替换为以下代码，以便创建 `SampleClass` 类  ：</span><span class="sxs-lookup"><span data-stu-id="c0764-181">Open the *SampleClass* class file in the code editor, and replace its contents with the following code to create the `SampleClass` class:</span></span>

   ```csharp
   using System;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceRuntime
   {
       public class SampleClass : ISampleInterface
       {
           private string p_UserInput;
           public string UserInput { get { return p_UserInput; } }

           public void GetUserInput()
           {
               Console.WriteLine("Please enter a value:");
               p_UserInput = Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports TypeEquivalenceInterface

   Public Class SampleClass
       Implements ISampleInterface

       Private p_UserInput As String
       Public ReadOnly Property UserInput() As String Implements ISampleInterface.UserInput
           Get
               Return p_UserInput
           End Get
       End Property

       Public Sub GetUserInput() Implements ISampleInterface.GetUserInput
           Console.WriteLine("Please enter a value:")
           p_UserInput = Console.ReadLine()
       End Sub
   End Class
   ```

1. <span data-ttu-id="c0764-182">选择“文件” > “保存全部”，或按 Ctrl+Shift+S 来保存文件和项目      。</span><span class="sxs-lookup"><span data-stu-id="c0764-182">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="c0764-183">在“解决方案资源管理器”中，右键单击 TypeEquivalenceRuntime 项目，并选择“生成”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-183">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="c0764-184">编译类库 DLL 文件，并保存到指定的生成输出路径中。</span><span class="sxs-lookup"><span data-stu-id="c0764-184">The class library DLL file is compiled and saved to the specified build output path.</span></span>

## <a name="create-a-client-project"></a><span data-ttu-id="c0764-185">创建客户端项目</span><span class="sxs-lookup"><span data-stu-id="c0764-185">Create a client project</span></span>

<span data-ttu-id="c0764-186">最后，创建引用接口程序集的类型等效性客户端程序。</span><span class="sxs-lookup"><span data-stu-id="c0764-186">Finally, create a type equivalence client program that references the interface assembly.</span></span>

1. <span data-ttu-id="c0764-187">在 Visual Studio 中，选择“文件” > “新建” > “项目”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-187">In Visual Studio, select **File** > **New** > **Project**.</span></span>

1. <span data-ttu-id="c0764-188">在“创建新项目”对话框中，在“搜索模板”框中键入“控制台”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-188">In the **Create a new project** dialog box, type *console* in the **Search for templates** box.</span></span> <span data-ttu-id="c0764-189">从列表中选择 C# 或 Visual Basic“控制台应用(.NET Framework)”模板，然后选择“下一步”   。</span><span class="sxs-lookup"><span data-stu-id="c0764-189">Select either the C# or Visual Basic **Console App (.NET Framework)** template from the list, and then select **Next**.</span></span>

1. <span data-ttu-id="c0764-190">在“配置新项目”对话框的“项目名称”下，键入“TypeEquivalenceClient”，然后选择“创建”     。</span><span class="sxs-lookup"><span data-stu-id="c0764-190">In the **Configure your new project** dialog box, under **Project name**, type *TypeEquivalenceClient*, and then select **Create**.</span></span> <span data-ttu-id="c0764-191">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="c0764-191">The new project is created.</span></span>

1. <span data-ttu-id="c0764-192">在“解决方案资源管理器”中，右键单击 TypeEquivalenceClient 项目，并选择“属性”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-192">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Properties**.</span></span>

1. <span data-ttu-id="c0764-193">在“属性”屏幕的左窗格中选择“生成”，然后将“输出路径”设置为用于 TypeEquivalenceInterface 项目的同一位置（例如 C:\TypeEquivalenceSample）     。</span><span class="sxs-lookup"><span data-stu-id="c0764-193">Select **Build** on the left pane of the **Properties** screen, and then set the **Output path** to the same location you used for the TypeEquivalenceInterface project, for example, *C:\TypeEquivalenceSample*.</span></span>

1. <span data-ttu-id="c0764-194">在“解决方案资源管理器”中，右键单击 TypeEquivalenceClient 项目，并选择“添加” > “引用”     。</span><span class="sxs-lookup"><span data-stu-id="c0764-194">In **Solution Explorer**, right-click the **TypeEquivalenceClient** project and select **Add** > **Reference**.</span></span>

1. <span data-ttu-id="c0764-195">如果 TypeEquivalenceInterface.dll 文件已在“引用管理器”对话框中列出，则选择该文件   。</span><span class="sxs-lookup"><span data-stu-id="c0764-195">In the **Reference Manager** dialog, if the **TypeEquivalenceInterface.dll** file is already listed, select it.</span></span> <span data-ttu-id="c0764-196">如果没有，请选择“浏览”，浏览到输出路径文件夹，选择 TypeEquivalenceInterface.dll 文件（而不是 TypeEquivalenceRuntime.dll 文件），并选择“添加”     。</span><span class="sxs-lookup"><span data-stu-id="c0764-196">If not, select **Browse**, browse to the output path folder, select the *TypeEquivalenceInterface.dll* file (not the *TypeEquivalenceRuntime.dll*), and select **Add**.</span></span> <span data-ttu-id="c0764-197">选择“确定”  。</span><span class="sxs-lookup"><span data-stu-id="c0764-197">Select **OK**.</span></span>

1. <span data-ttu-id="c0764-198">在“解决方案资源管理器”中，展开“引用”文件夹，并选择“TypeEquivalenceInterface”引用    。</span><span class="sxs-lookup"><span data-stu-id="c0764-198">In **Solution Explorer**, expand the **References** folder and select the **TypeEquivalenceInterface** reference.</span></span> <span data-ttu-id="c0764-199">在“属性”窗格中，将“嵌入式互操作类型”设置为“True”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-199">In the **Properties** pane, set **Embed Interop Types** to **True**.</span></span>

1. <span data-ttu-id="c0764-200">在代码编辑器中打开 Program.cs 或 Module1.vb 文件，将其内容替换为以下代码，以便创建客户端程序   ：</span><span class="sxs-lookup"><span data-stu-id="c0764-200">Open the *Program.cs* or *Module1.vb* file in the code editor, and replace its contents with the following code to create the client program:</span></span>

   ```csharp
   using System;
   using System.Reflection;
   using TypeEquivalenceInterface;

   namespace TypeEquivalenceClient
   {
       class Program
       {
           static void Main(string[] args)
           {
               Assembly sampleAssembly = Assembly.Load("TypeEquivalenceRuntime");
               ISampleInterface sampleClass =
                   (ISampleInterface)sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass");
               sampleClass.GetUserInput();
               Console.WriteLine(sampleClass.UserInput);
               Console.WriteLine(sampleAssembly.GetName().Version.ToString());
               Console.ReadLine();
           }
       }
   }
   ```

   ```vb
   Imports System.Reflection
   Imports TypeEquivalenceInterface

   Module Module1

       Sub Main()
           Dim sampleAssembly = Assembly.Load("TypeEquivalenceRuntime")
           Dim sampleClass As ISampleInterface = CType( _
               sampleAssembly.CreateInstance("TypeEquivalenceRuntime.SampleClass"), ISampleInterface)
           sampleClass.GetUserInput()
           Console.WriteLine(sampleClass.UserInput)
           Console.WriteLine(sampleAssembly.GetName().Version)
           Console.ReadLine()
       End Sub

   End Module
   ```

1. <span data-ttu-id="c0764-201">选择“文件” > “保存全部”，或按 Ctrl+Shift+S 来保存文件和项目      。</span><span class="sxs-lookup"><span data-stu-id="c0764-201">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="c0764-202">按 Ctrl+F5 生成并运行程序   。</span><span class="sxs-lookup"><span data-stu-id="c0764-202">Press **Ctrl**+**F5** to build and run the program.</span></span> <span data-ttu-id="c0764-203">请注意，控制台输出返回程序集版本 1.0.0.0  。</span><span class="sxs-lookup"><span data-stu-id="c0764-203">Note that the console output returns the assembly version **1.0.0.0**.</span></span>

## <a name="modify-the-interface"></a><span data-ttu-id="c0764-204">修改接口</span><span class="sxs-lookup"><span data-stu-id="c0764-204">Modify the interface</span></span>

<span data-ttu-id="c0764-205">现在，修改接口程序集，并更改其版本。</span><span class="sxs-lookup"><span data-stu-id="c0764-205">Now, modify the interface assembly, and change its version.</span></span>

1. <span data-ttu-id="c0764-206">在 Visual Studio 中，选择“文件” > “打开” > 项目/解决方案，并打开 TypeEquivalenceInterface 项目     。</span><span class="sxs-lookup"><span data-stu-id="c0764-206">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceInterface** project.</span></span>

1. <span data-ttu-id="c0764-207">在“解决方案资源管理器”中，右键单击 TypeEquivalenceInterface 项目，并选择“属性”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-207">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Properties**.</span></span>

1. <span data-ttu-id="c0764-208">在“属性”屏幕的左窗格中选择“应用程序”，然后选择“程序集信息”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-208">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="c0764-209">在“程序集信息”对话框中，将“程序集版本”和“文件版本”值更改为 2.0.0.0，然后选择“确定”      。</span><span class="sxs-lookup"><span data-stu-id="c0764-209">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="c0764-210">打开 SampleInterface.cs 或 SampleInterface.vb 文件，并将以下代码行添加到 `ISampleInterface` 接口   ：</span><span class="sxs-lookup"><span data-stu-id="c0764-210">Open the *SampleInterface.cs* or *SampleInterface.vb* file, and add the following line of code to the `ISampleInterface` interface:</span></span>

   ```csharp
   DateTime GetDate();
   ```

   ```vb
   Function GetDate() As Date
   ```

1. <span data-ttu-id="c0764-211">选择“文件” > “保存全部”，或按 Ctrl+Shift+S 来保存文件和项目      。</span><span class="sxs-lookup"><span data-stu-id="c0764-211">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="c0764-212">在“解决方案资源管理器”中，右键单击 TypeEquivalenceInterface 项目，然后选择“生成”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-212">In **Solution Explorer**, right-click the **TypeEquivalenceInterface** project and select **Build**.</span></span> <span data-ttu-id="c0764-213">编译类库 DLL 文件的新版本，并保存到生成输出路径中。</span><span class="sxs-lookup"><span data-stu-id="c0764-213">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="modify-the-runtime-class"></a><span data-ttu-id="c0764-214">修改运行时类</span><span class="sxs-lookup"><span data-stu-id="c0764-214">Modify the runtime class</span></span>

<span data-ttu-id="c0764-215">修改运行时类的同时更新其版本。</span><span class="sxs-lookup"><span data-stu-id="c0764-215">Also modify the runtime class and update its version.</span></span>

1. <span data-ttu-id="c0764-216">在 Visual Studio 中，选择“文件” > “打开” > 项目/解决方案，并打开 TypeEquivalenceRuntime 项目     。</span><span class="sxs-lookup"><span data-stu-id="c0764-216">In Visual Studio, select **File** > **Open** > **Project/Solution**, and open the **TypeEquivalenceRuntime** project.</span></span>

1. <span data-ttu-id="c0764-217">在“解决方案资源管理器”中，右键单击 TypeEquivalenceRuntime 项目，并选择“属性”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-217">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Properties**.</span></span>

1. <span data-ttu-id="c0764-218">在“属性”屏幕的左窗格中选择“应用程序”，然后选择“程序集信息”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-218">Select **Application** on the left pane of the **Properties** screen, and then select **Assembly Information**.</span></span>

1. <span data-ttu-id="c0764-219">在“程序集信息”对话框中，将“程序集版本”和“文件版本”值更改为 2.0.0.0，然后选择“确定”      。</span><span class="sxs-lookup"><span data-stu-id="c0764-219">In the **Assembly Information** dialog box, change the **Assembly version** and **File version** values to *2.0.0.0*, and then select **OK**.</span></span>

1. <span data-ttu-id="c0764-220">打开 SampleClass.cs 或 SampleClass.vb 文件，并将以下代码添加到 `SampleClass` 类   ：</span><span class="sxs-lookup"><span data-stu-id="c0764-220">Open the *SampleClass.cs* or *SampleClass.vb* file, and add the following code to the `SampleClass` class:</span></span>

   ```csharp
    public DateTime GetDate()
    {
        return DateTime.Now;
    }
   ```

   ```vb
   Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
       Return Now
   End Function
   ```

1. <span data-ttu-id="c0764-221">选择“文件” > “保存全部”，或按 Ctrl+Shift+S 来保存文件和项目      。</span><span class="sxs-lookup"><span data-stu-id="c0764-221">Select **File** > **Save All** or press **Ctrl**+**Shift**+**S** to save the files and project.</span></span>

1. <span data-ttu-id="c0764-222">在“解决方案资源管理器”中，右键单击 TypeEquivalenceRuntime 项目，并选择“生成”    。</span><span class="sxs-lookup"><span data-stu-id="c0764-222">In **Solution Explorer**, right-click the **TypeEquivalenceRuntime** project and select **Build**.</span></span> <span data-ttu-id="c0764-223">编译类库 DLL 文件的新版本，并保存到生成输出路径中。</span><span class="sxs-lookup"><span data-stu-id="c0764-223">A new version of the class library DLL file is compiled and saved to the build output path.</span></span>

## <a name="run-the-updated-client-program"></a><span data-ttu-id="c0764-224">运行更新的客户端程序</span><span class="sxs-lookup"><span data-stu-id="c0764-224">Run the updated client program</span></span>

<span data-ttu-id="c0764-225">转到生成输出文件夹位置，并运行 TypeEquivalenceClient.exe  。</span><span class="sxs-lookup"><span data-stu-id="c0764-225">Go to the build output folder location and run *TypeEquivalenceClient.exe*.</span></span> <span data-ttu-id="c0764-226">请注意，控制台输出现在反映 `TypeEquivalenceRuntime` 程序集的新版本（即 2.0.0.0），而不会重新编译程序  。</span><span class="sxs-lookup"><span data-stu-id="c0764-226">Note that the console output now reflects the new version of the `TypeEquivalenceRuntime` assembly, *2.0.0.0*, without the program being recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="c0764-227">请参阅</span><span class="sxs-lookup"><span data-stu-id="c0764-227">See also</span></span>

- [<span data-ttu-id="c0764-228">-link（C# 编译器选项）</span><span class="sxs-lookup"><span data-stu-id="c0764-228">-link (C# Compiler Options)</span></span>](../../csharp/language-reference/compiler-options/link-compiler-option.md)
- [<span data-ttu-id="c0764-229">-link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0764-229">-link (Visual Basic)</span></span>](../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="c0764-230">C# 编程指南</span><span class="sxs-lookup"><span data-stu-id="c0764-230">C# programming guide</span></span>](../../csharp/programming-guide/index.md)
- [<span data-ttu-id="c0764-231">编程概念 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c0764-231">Programming concepts (Visual Basic)</span></span>](../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="c0764-232">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="c0764-232">Assemblies in .NET</span></span>](index.md)
