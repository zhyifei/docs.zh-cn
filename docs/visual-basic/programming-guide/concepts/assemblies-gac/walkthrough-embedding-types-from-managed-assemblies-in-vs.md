---
title: 演练：在 Visual Studio (Visual Basic 中) 中嵌入托管程序集中的类型
ms.date: 07/20/2015
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
ms.openlocfilehash: 836d035aab06f18c13e3675fbd72c5ab9879a3d2
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359450"
---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="bda47-102">演练：在 Visual Studio (Visual Basic 中) 中嵌入托管程序集中的类型</span><span class="sxs-lookup"><span data-stu-id="bda47-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>

<span data-ttu-id="bda47-103">如果嵌入强命名托管程序集中的类型信息，则可以对应用程序中的类型进行松耦合，以实现版本独立性。</span><span class="sxs-lookup"><span data-stu-id="bda47-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="bda47-104">也就是说，可以将程序编写为使用多个托管库版本中的类型，而不必对每个版本重新编译程序。</span><span class="sxs-lookup"><span data-stu-id="bda47-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>

<span data-ttu-id="bda47-105">类型嵌入经常与 COM 互操作一起使用，例如使用 Microsoft Office 中的自动化对象的应用程序。</span><span class="sxs-lookup"><span data-stu-id="bda47-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="bda47-106">通过嵌入类型信息，程序的同一个版本可以处理不同计算机上的不同 Microsoft Office 版本。</span><span class="sxs-lookup"><span data-stu-id="bda47-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="bda47-107">但也可以在完全托管的解决方案中使用类型嵌入。</span><span class="sxs-lookup"><span data-stu-id="bda47-107">However, you can also use type embedding with a fully managed solution.</span></span>

<span data-ttu-id="bda47-108">可从具有以下特征的程序集嵌入类型信息：</span><span class="sxs-lookup"><span data-stu-id="bda47-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>

- <span data-ttu-id="bda47-109">程序集至少公开一个公共接口。</span><span class="sxs-lookup"><span data-stu-id="bda47-109">The assembly exposes at least one public interface.</span></span>

- <span data-ttu-id="bda47-110">嵌入的接口使用 `ComImport` 特性和 `Guid` 特性（及一个唯一 GUID）进行批注。</span><span class="sxs-lookup"><span data-stu-id="bda47-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>

- <span data-ttu-id="bda47-111">程序集使用 `ImportedFromTypeLib` 特性或 `PrimaryInteropAssembly` 特性和程序集级别的 `Guid` 特性进行批注。</span><span class="sxs-lookup"><span data-stu-id="bda47-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="bda47-112">(默认情况下，Visual Basic 项目模板包含程序集级别`Guid`属性。)</span><span class="sxs-lookup"><span data-stu-id="bda47-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>

<span data-ttu-id="bda47-113">指定可嵌入的公共接口后，可以创建实现这些接口的运行时类。</span><span class="sxs-lookup"><span data-stu-id="bda47-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="bda47-114">然后，客户端程序可以通过引用包含这些公共接口的程序集，并将该引用的 `Embed Interop Types` 属性设置为 `True`，在设计时嵌入这些接口的类型信息。</span><span class="sxs-lookup"><span data-stu-id="bda47-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="bda47-115">这等效于使用命令行编译器和通过 `/link` 编译器选项引用该程序集。</span><span class="sxs-lookup"><span data-stu-id="bda47-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="bda47-116">然后，客户端程序可以加载类型化为这些接口的运行时对象的实例。</span><span class="sxs-lookup"><span data-stu-id="bda47-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="bda47-117">如果创建新版本的强命名运行时程序集，则不必使用更新的运行时程序集来重新编译客户端程序。</span><span class="sxs-lookup"><span data-stu-id="bda47-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="bda47-118">客户端程序将使用公共接口的嵌入类型信息，从而继续使用任何可用的运行时程序集版本。</span><span class="sxs-lookup"><span data-stu-id="bda47-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>

<span data-ttu-id="bda47-119">由于类型嵌入的主要功能是提供对 COM 互操作程序集中类型信息的嵌入的支持，因此以下限制在将类型信息嵌入完全托管解决方案中时适用：</span><span class="sxs-lookup"><span data-stu-id="bda47-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>

- <span data-ttu-id="bda47-120">仅嵌入特定于 COM 互操作的特性；忽略其他特性。</span><span class="sxs-lookup"><span data-stu-id="bda47-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>

- <span data-ttu-id="bda47-121">如果一个类型使用泛型参数且泛型参数的类型是嵌入类型，则不能跨程序集边界使用该类型。</span><span class="sxs-lookup"><span data-stu-id="bda47-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="bda47-122">跨程序集边界的示例包括从另一个程序集调用方法或从另一个程序集中定义的类型派生类型。</span><span class="sxs-lookup"><span data-stu-id="bda47-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>

- <span data-ttu-id="bda47-123">不嵌入常量。</span><span class="sxs-lookup"><span data-stu-id="bda47-123">Constants are not embedded.</span></span>

- <span data-ttu-id="bda47-124"><xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> 类不支持将嵌入类型作为密钥。</span><span class="sxs-lookup"><span data-stu-id="bda47-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType> class does not support an embedded type as a key.</span></span> <span data-ttu-id="bda47-125">可以实现自己的字典类型以支持将嵌入类型作为密钥。</span><span class="sxs-lookup"><span data-stu-id="bda47-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>

 <span data-ttu-id="bda47-126">本演练中将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="bda47-126">In this walkthrough, you will do the following:</span></span>

- <span data-ttu-id="bda47-127">创建一个强命名程序集，它具有包含可嵌入类型信息的公共接口。</span><span class="sxs-lookup"><span data-stu-id="bda47-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>

- <span data-ttu-id="bda47-128">创建一个实现该公共接口的强命名运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="bda47-128">Create a strong-named runtime assembly that implements that public interface.</span></span>

- <span data-ttu-id="bda47-129">创建一个客户端程序，该程序嵌入公共接口中的类型信息，并创建运行时程序集中的类的实例。</span><span class="sxs-lookup"><span data-stu-id="bda47-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>

- <span data-ttu-id="bda47-130">修改并重新生成运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="bda47-130">Modify and rebuild the runtime assembly.</span></span>

- <span data-ttu-id="bda47-131">运行客户端程序，查看正在使用的运行时程序集新版本，而不必重新编译该客户端程序。</span><span class="sxs-lookup"><span data-stu-id="bda47-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="creating-an-interface"></a><span data-ttu-id="bda47-132">创建接口</span><span class="sxs-lookup"><span data-stu-id="bda47-132">Creating an Interface</span></span>

#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="bda47-133">创建类型等效性接口项目</span><span class="sxs-lookup"><span data-stu-id="bda47-133">To create the type equivalence interface project</span></span>

1. <span data-ttu-id="bda47-134">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="bda47-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="bda47-135">在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。</span><span class="sxs-lookup"><span data-stu-id="bda47-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="bda47-136">在“模板”窗格中，选择“类库”。</span><span class="sxs-lookup"><span data-stu-id="bda47-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="bda47-137">在“名称”框中，键入 `TypeEquivalenceInterface`，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="bda47-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="bda47-138">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="bda47-138">The new project is created.</span></span>

3. <span data-ttu-id="bda47-139">在中**解决方案资源管理器**，右键单击 Class1.vb 文件，然后单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="bda47-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="bda47-140">将文件重命名为 `ISampleInterface.vb`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="bda47-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="bda47-141">重命名文件也会将类重命名为 `ISampleInterface`。</span><span class="sxs-lookup"><span data-stu-id="bda47-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="bda47-142">此类将表示类的公共接口。</span><span class="sxs-lookup"><span data-stu-id="bda47-142">This class will represent the public interface for the class.</span></span>

4. <span data-ttu-id="bda47-143">右键单击 TypeEquivalenceInterface 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="bda47-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="bda47-144">单击“编译”选项卡。将输出路径设置为开发计算机上的有效位置，例如 `C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="bda47-144">Click the **Compile** tab. Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="bda47-145">本演练的后续步骤中也将使用此位置。</span><span class="sxs-lookup"><span data-stu-id="bda47-145">This location will also be used in a later step in this walkthrough.</span></span>

5. <span data-ttu-id="bda47-146">在编辑项目属性期间，单击“签名”选项卡。选择“为程序集签名”选项。</span><span class="sxs-lookup"><span data-stu-id="bda47-146">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="bda47-147">在“选择强名称密钥文件”列表中，单击“<新建…>”。</span><span class="sxs-lookup"><span data-stu-id="bda47-147">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="bda47-148">在“密钥文件名”框中，键入 `key.snk`。</span><span class="sxs-lookup"><span data-stu-id="bda47-148">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="bda47-149">清除“使用密码保护密钥文件”复选框。</span><span class="sxs-lookup"><span data-stu-id="bda47-149">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="bda47-150">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bda47-150">Click **OK**.</span></span>

6. <span data-ttu-id="bda47-151">打开 ISampleInterface.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="bda47-151">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="bda47-152">将以下代码添加到 ISampleInterface 类文件，以创建 ISampleInterface 接口。</span><span class="sxs-lookup"><span data-stu-id="bda47-152">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>

    ```vb
    Imports System.Runtime.InteropServices

    <ComImport()>
    <Guid("8DA56996-A151-4136-B474-32784559F6DF")>
    Public Interface ISampleInterface
        Sub GetUserInput()
        ReadOnly Property UserInput As String
    End Interface
    ```

7. <span data-ttu-id="bda47-153">在“工具”菜单上，单击“创建 Guid”。</span><span class="sxs-lookup"><span data-stu-id="bda47-153">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="bda47-154">在“创建 GUID”对话框中，单击“注册表格式”，然后单击“复制”。</span><span class="sxs-lookup"><span data-stu-id="bda47-154">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="bda47-155">单击“退出” 。</span><span class="sxs-lookup"><span data-stu-id="bda47-155">Click **Exit**.</span></span>

8. <span data-ttu-id="bda47-156">在 `Guid` 特性中，删除示例 GUID ，并粘贴从“创建 GUID”对话框复制的 GUID。</span><span class="sxs-lookup"><span data-stu-id="bda47-156">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="bda47-157">删除复制的 GUID 中的大括号 ({})。</span><span class="sxs-lookup"><span data-stu-id="bda47-157">Remove the braces ({}) from the copied GUID.</span></span>

9. <span data-ttu-id="bda47-158">在“项目”菜单上，单击“显示所有文件”。</span><span class="sxs-lookup"><span data-stu-id="bda47-158">On the **Project** menu, click **Show All Files**.</span></span>

10. <span data-ttu-id="bda47-159">在中**解决方案资源管理器**，展开**我的项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="bda47-159">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="bda47-160">双击 AssemblyInfo.vb。</span><span class="sxs-lookup"><span data-stu-id="bda47-160">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="bda47-161">向文件中添加以下特性。</span><span class="sxs-lookup"><span data-stu-id="bda47-161">Add the following attribute to the file.</span></span>

    ```vb
    <Assembly: ImportedFromTypeLib("")>
    ```

    <span data-ttu-id="bda47-162">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="bda47-162">Save the file.</span></span>

11. <span data-ttu-id="bda47-163">保存项目。</span><span class="sxs-lookup"><span data-stu-id="bda47-163">Save the project.</span></span>

12. <span data-ttu-id="bda47-164">右键单击 TypeEquivalenceInterface 项目，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="bda47-164">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="bda47-165">此时将编译类库 .dll 文件，并保存到指定的生成输出路径中（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="bda47-165">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="creating-a-runtime-class"></a><span data-ttu-id="bda47-166">创建运行时类</span><span class="sxs-lookup"><span data-stu-id="bda47-166">Creating a Runtime Class</span></span>

#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="bda47-167">创建类型等效性运行时项目</span><span class="sxs-lookup"><span data-stu-id="bda47-167">To create the type equivalence runtime project</span></span>

1. <span data-ttu-id="bda47-168">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="bda47-168">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="bda47-169">在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。</span><span class="sxs-lookup"><span data-stu-id="bda47-169">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="bda47-170">在“模板”窗格中，选择“类库”。</span><span class="sxs-lookup"><span data-stu-id="bda47-170">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="bda47-171">在“名称”框中，键入 `TypeEquivalenceRuntime`，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="bda47-171">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="bda47-172">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="bda47-172">The new project is created.</span></span>

3. <span data-ttu-id="bda47-173">在中**解决方案资源管理器**，右键单击 Class1.vb 文件，然后单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="bda47-173">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="bda47-174">将文件重命名为 `SampleClass.vb`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="bda47-174">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="bda47-175">重命名文件也会将类重命名为 `SampleClass`。</span><span class="sxs-lookup"><span data-stu-id="bda47-175">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="bda47-176">此类将实现 `ISampleInterface` 接口。</span><span class="sxs-lookup"><span data-stu-id="bda47-176">This class will implement the `ISampleInterface` interface.</span></span>

4. <span data-ttu-id="bda47-177">右键单击 TypeEquivalenceRuntime 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="bda47-177">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="bda47-178">单击“编译”选项卡。将输出路径设置为 TypeEquivalenceInterface 项目中所用的同一位置，例如，`C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="bda47-178">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>

5. <span data-ttu-id="bda47-179">在编辑项目属性期间，单击“签名”选项卡。选择“为程序集签名”选项。</span><span class="sxs-lookup"><span data-stu-id="bda47-179">While still editing the project properties, click the **Signing** tab. Select the **Sign the assembly** option.</span></span> <span data-ttu-id="bda47-180">在“选择强名称密钥文件”列表中，单击“<新建…>”。</span><span class="sxs-lookup"><span data-stu-id="bda47-180">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="bda47-181">在“密钥文件名”框中，键入 `key.snk`。</span><span class="sxs-lookup"><span data-stu-id="bda47-181">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="bda47-182">清除“使用密码保护密钥文件”复选框。</span><span class="sxs-lookup"><span data-stu-id="bda47-182">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="bda47-183">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="bda47-183">Click **OK**.</span></span>

6. <span data-ttu-id="bda47-184">右键单击 TypeEquivalenceRuntime 项目，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="bda47-184">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="bda47-185">单击“浏览”选项卡，然后浏览到输出路径文件夹。</span><span class="sxs-lookup"><span data-stu-id="bda47-185">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="bda47-186">选择 TypeEquivalenceInterface.dll 文件并单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="bda47-186">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>

7. <span data-ttu-id="bda47-187">在“项目”菜单上，单击“显示所有文件”。</span><span class="sxs-lookup"><span data-stu-id="bda47-187">On the **Project** menu, click **Show All Files**.</span></span>

8. <span data-ttu-id="bda47-188">在“解决方案资源管理器”中，展开“引用”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bda47-188">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="bda47-189">选择 TypeEquivalenceInterface 引用。</span><span class="sxs-lookup"><span data-stu-id="bda47-189">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="bda47-190">在 TypeEquivalenceInterface 引用的“属性”窗口中，将“特定版本”属性设置为“False”。</span><span class="sxs-lookup"><span data-stu-id="bda47-190">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>

9. <span data-ttu-id="bda47-191">将以下代码添加到 SampleClass 类文件，以创建 SampleClass 类。</span><span class="sxs-lookup"><span data-stu-id="bda47-191">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>

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

10. <span data-ttu-id="bda47-192">保存项目。</span><span class="sxs-lookup"><span data-stu-id="bda47-192">Save the project.</span></span>

11. <span data-ttu-id="bda47-193">右键单击 TypeEquivalenceRuntime 项目，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="bda47-193">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="bda47-194">此时将编译类库 .dll 文件，并保存到指定的生成输出路径中（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="bda47-194">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="creating-a-client-project"></a><span data-ttu-id="bda47-195">创建客户端项目</span><span class="sxs-lookup"><span data-stu-id="bda47-195">Creating a Client Project</span></span>

#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="bda47-196">创建类型等效性客户端项目</span><span class="sxs-lookup"><span data-stu-id="bda47-196">To create the type equivalence client project</span></span>

1. <span data-ttu-id="bda47-197">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="bda47-197">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>

2. <span data-ttu-id="bda47-198">在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。</span><span class="sxs-lookup"><span data-stu-id="bda47-198">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="bda47-199">在“模板”窗格中，选择“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="bda47-199">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="bda47-200">在“名称”框中，键入 `TypeEquivalenceClient`，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="bda47-200">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="bda47-201">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="bda47-201">The new project is created.</span></span>

3. <span data-ttu-id="bda47-202">右键单击 TypeEquivalenceClient 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="bda47-202">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="bda47-203">单击“编译”选项卡。将输出路径设置为 TypeEquivalenceInterface 项目中所用的同一位置，例如，`C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="bda47-203">Click the **Compile** tab. Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>

4. <span data-ttu-id="bda47-204">右键单击 TypeEquivalenceClient 项目，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="bda47-204">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="bda47-205">单击“浏览”选项卡，然后浏览到输出路径文件夹。</span><span class="sxs-lookup"><span data-stu-id="bda47-205">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="bda47-206">选择 TypeEquivalenceInterface.dll 文件（不是 TypeEquivalenceRuntime.dll）并单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="bda47-206">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>

5. <span data-ttu-id="bda47-207">在“项目”菜单上，单击“显示所有文件”。</span><span class="sxs-lookup"><span data-stu-id="bda47-207">On the **Project** menu, click **Show All Files**.</span></span>

6. <span data-ttu-id="bda47-208">在“解决方案资源管理器”中，展开“引用”文件夹。</span><span class="sxs-lookup"><span data-stu-id="bda47-208">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="bda47-209">选择 TypeEquivalenceInterface 引用。</span><span class="sxs-lookup"><span data-stu-id="bda47-209">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="bda47-210">在 TypeEquivalenceInterface 引用的“属性”窗口中，将“嵌入互操作类型”属性设置为“True”。</span><span class="sxs-lookup"><span data-stu-id="bda47-210">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>

7. <span data-ttu-id="bda47-211">将以下代码添加到 Module1.vb 文件以创建客户端程序。</span><span class="sxs-lookup"><span data-stu-id="bda47-211">Add the following code to the Module1.vb file to create the client program.</span></span>

    ```vb
    Imports TypeEquivalenceInterface
    Imports System.Reflection

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

8. <span data-ttu-id="bda47-212">按 Ctrl+F5 生成并运行程序。</span><span class="sxs-lookup"><span data-stu-id="bda47-212">Press CTRL+F5 to build and run the program.</span></span>

## <a name="modifying-the-interface"></a><span data-ttu-id="bda47-213">修改接口</span><span class="sxs-lookup"><span data-stu-id="bda47-213">Modifying the Interface</span></span>

#### <a name="to-modify-the-interface"></a><span data-ttu-id="bda47-214">修改接口</span><span class="sxs-lookup"><span data-stu-id="bda47-214">To modify the interface</span></span>

1. <span data-ttu-id="bda47-215">在 Visual Studio 中的“文件”菜单上，指向“打开”，然后单击“项目/解决方案”。</span><span class="sxs-lookup"><span data-stu-id="bda47-215">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>

2. <span data-ttu-id="bda47-216">在“打开项目”对话框中，右键单击 TypeEquivalenceInterface 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="bda47-216">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="bda47-217">单击“应用程序”  选项卡。单击“程序集信息”按钮。</span><span class="sxs-lookup"><span data-stu-id="bda47-217">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="bda47-218">将“程序集版本”和“文件版本”的值更改为 `2.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="bda47-218">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>

3. <span data-ttu-id="bda47-219">打开 ISampleInterface.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="bda47-219">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="bda47-220">将以下代码行添加到 ISampleInterface 接口。</span><span class="sxs-lookup"><span data-stu-id="bda47-220">Add the following line of code to the ISampleInterface interface.</span></span>

    ```vb
    Function GetDate() As Date
    ```

    <span data-ttu-id="bda47-221">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="bda47-221">Save the file.</span></span>

4. <span data-ttu-id="bda47-222">保存项目。</span><span class="sxs-lookup"><span data-stu-id="bda47-222">Save the project.</span></span>

5. <span data-ttu-id="bda47-223">右键单击 TypeEquivalenceInterface 项目，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="bda47-223">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="bda47-224">此时将编译新版本的类库 .dll 文件，并保存到指定的生成输出路径中（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="bda47-224">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

## <a name="modifying-the-runtime-class"></a><span data-ttu-id="bda47-225">修改运行时类</span><span class="sxs-lookup"><span data-stu-id="bda47-225">Modifying the Runtime Class</span></span>

#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="bda47-226">修改运行时类</span><span class="sxs-lookup"><span data-stu-id="bda47-226">To modify the runtime class</span></span>

1. <span data-ttu-id="bda47-227">在 Visual Studio 中的“文件”菜单上，指向“打开”，然后单击“项目/解决方案”。</span><span class="sxs-lookup"><span data-stu-id="bda47-227">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>

2. <span data-ttu-id="bda47-228">在“打开项目”对话框中，右键单击 TypeEquivalenceRuntime 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="bda47-228">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="bda47-229">单击“应用程序”  选项卡。单击“程序集信息”按钮。</span><span class="sxs-lookup"><span data-stu-id="bda47-229">Click the **Application** tab. Click the **Assembly Information** button.</span></span> <span data-ttu-id="bda47-230">将“程序集版本”和“文件版本”的值更改为 `2.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="bda47-230">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>

3. <span data-ttu-id="bda47-231">打开 SampleClass.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="bda47-231">Open the SampleClass.vb file.</span></span> <span data-ttu-id="bda47-232">将以下代码行添加到 SampleClass 类。</span><span class="sxs-lookup"><span data-stu-id="bda47-232">Add the following lines of code to the SampleClass class.</span></span>

```vb
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate
    Return Now
End Function
```

    Save the file.

4. <span data-ttu-id="bda47-233">保存项目。</span><span class="sxs-lookup"><span data-stu-id="bda47-233">Save the project.</span></span>

5. <span data-ttu-id="bda47-234">右键单击 TypeEquivalenceRuntime 项目，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="bda47-234">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="bda47-235">此时将编译更新版本的类库 .dll 文件，并保存到之前指定的生成输出路径中（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="bda47-235">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>

6. <span data-ttu-id="bda47-236">在文件资源管理器中，打开输出路径文件夹（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="bda47-236">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="bda47-237">双击 TypeEquivalenceClient.exe 运行该程序。</span><span class="sxs-lookup"><span data-stu-id="bda47-237">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="bda47-238">程序将反映 TypeEquivalenceRuntime 程序集的未经重新编译的新版本。</span><span class="sxs-lookup"><span data-stu-id="bda47-238">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>

## <a name="see-also"></a><span data-ttu-id="bda47-239">请参阅</span><span class="sxs-lookup"><span data-stu-id="bda47-239">See also</span></span>

- [<span data-ttu-id="bda47-240">/link (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bda47-240">/link (Visual Basic)</span></span>](../../../../visual-basic/reference/command-line-compiler/link.md)
- [<span data-ttu-id="bda47-241">编程概念</span><span class="sxs-lookup"><span data-stu-id="bda47-241">Programming Concepts</span></span>](../../../../visual-basic/programming-guide/concepts/index.md)
- [<span data-ttu-id="bda47-242">使用程序集编程</span><span class="sxs-lookup"><span data-stu-id="bda47-242">Programming with Assemblies</span></span>](../../../../framework/app-domains/programming-with-assemblies.md)
- [<span data-ttu-id="bda47-243">.NET 中的程序集</span><span class="sxs-lookup"><span data-stu-id="bda47-243">Assemblies in .NET</span></span>](../../../../standard/assembly/index.md)
