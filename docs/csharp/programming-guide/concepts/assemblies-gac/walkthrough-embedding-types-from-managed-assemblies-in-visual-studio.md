---
title: "演练：在 Visual Studio 中嵌入托管程序集中的类型 (C#)"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 55ed13c9-c5bb-4bc2-bcd8-0587eb568864
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 7b003e76229a06883adc22f933f08663330f0c9d
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-c"></a><span data-ttu-id="909a1-102">演练：在 Visual Studio 中嵌入托管程序集中的类型 (C#)</span><span class="sxs-lookup"><span data-stu-id="909a1-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (C#)</span></span>
<span data-ttu-id="909a1-103">如果嵌入强命名托管程序集中的类型信息，则可以对应用程序中的类型进行松耦合，以实现版本独立性。</span><span class="sxs-lookup"><span data-stu-id="909a1-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="909a1-104">也就是说，可以将程序编写为使用多个托管库版本中的类型，而不必对每个版本重新编译程序。</span><span class="sxs-lookup"><span data-stu-id="909a1-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="909a1-105">类型嵌入经常与 COM 互操作一起使用，例如使用 Microsoft Office 中的自动化对象的应用程序。</span><span class="sxs-lookup"><span data-stu-id="909a1-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="909a1-106">通过嵌入类型信息，程序的同一个版本可以处理不同计算机上的不同 Microsoft Office 版本。</span><span class="sxs-lookup"><span data-stu-id="909a1-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="909a1-107">但也可以在完全托管的解决方案中使用类型嵌入。</span><span class="sxs-lookup"><span data-stu-id="909a1-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="909a1-108">可从具有以下特征的程序集嵌入类型信息：</span><span class="sxs-lookup"><span data-stu-id="909a1-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="909a1-109">程序集至少公开一个公共接口。</span><span class="sxs-lookup"><span data-stu-id="909a1-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="909a1-110">嵌入的接口使用 `ComImport` 特性和 `Guid` 特性（及一个唯一 GUID）进行批注。</span><span class="sxs-lookup"><span data-stu-id="909a1-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="909a1-111">程序集使用 `ImportedFromTypeLib` 特性或 `PrimaryInteropAssembly` 特性和程序集级别的 `Guid` 特性进行批注。</span><span class="sxs-lookup"><span data-stu-id="909a1-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="909a1-112">（默认情况下，Visual C# 项目模板包含程序集级别的 `Guid` 特性。）</span><span class="sxs-lookup"><span data-stu-id="909a1-112">(By default, Visual C# project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="909a1-113">指定可嵌入的公共接口后，可以创建实现这些接口的运行时类。</span><span class="sxs-lookup"><span data-stu-id="909a1-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="909a1-114">然后，客户端程序可以通过引用包含这些公共接口的程序集，并将该引用的 `Embed Interop Types` 属性设置为 `True`，在设计时嵌入这些接口的类型信息。</span><span class="sxs-lookup"><span data-stu-id="909a1-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="909a1-115">这等效于使用命令行编译器和通过 `/link` 编译器选项引用该程序集。</span><span class="sxs-lookup"><span data-stu-id="909a1-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="909a1-116">然后，客户端程序可以加载类型化为这些接口的运行时对象的实例。</span><span class="sxs-lookup"><span data-stu-id="909a1-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="909a1-117">如果创建新版本的强命名运行时程序集，则不必使用更新的运行时程序集来重新编译客户端程序。</span><span class="sxs-lookup"><span data-stu-id="909a1-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="909a1-118">客户端程序将使用公共接口的嵌入类型信息，从而继续使用任何可用的运行时程序集版本。</span><span class="sxs-lookup"><span data-stu-id="909a1-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="909a1-119">由于类型嵌入的主要功能是提供对 COM 互操作程序集中类型信息的嵌入的支持，因此以下限制在将类型信息嵌入完全托管解决方案中时适用：</span><span class="sxs-lookup"><span data-stu-id="909a1-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="909a1-120">仅嵌入特定于 COM 互操作的特性；忽略其他特性。</span><span class="sxs-lookup"><span data-stu-id="909a1-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="909a1-121">如果一个类型使用泛型参数且泛型参数的类型是嵌入类型，则不能跨程序集边界使用该类型。</span><span class="sxs-lookup"><span data-stu-id="909a1-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="909a1-122">跨程序集边界的示例包括从另一个程序集调用方法或从另一个程序集中定义的类型派生类型。</span><span class="sxs-lookup"><span data-stu-id="909a1-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="909a1-123">不嵌入常量。</span><span class="sxs-lookup"><span data-stu-id="909a1-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="909a1-124"><xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> 类不支持将嵌入类型作为密钥。</span><span class="sxs-lookup"><span data-stu-id="909a1-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> class does not support an embedded type as a key.</span></span> <span data-ttu-id="909a1-125">可以实现自己的字典类型以支持将嵌入类型作为密钥。</span><span class="sxs-lookup"><span data-stu-id="909a1-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="909a1-126">本演练中将执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="909a1-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="909a1-127">创建一个强命名程序集，它具有包含可嵌入类型信息的公共接口。</span><span class="sxs-lookup"><span data-stu-id="909a1-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="909a1-128">创建一个实现该公共接口的强命名运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="909a1-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="909a1-129">创建一个客户端程序，该程序嵌入公共接口中的类型信息，并创建运行时程序集中的类的实例。</span><span class="sxs-lookup"><span data-stu-id="909a1-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="909a1-130">修改并重新生成运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="909a1-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="909a1-131">运行客户端程序，查看正在使用的运行时程序集新版本，而不必重新编译该客户端程序。</span><span class="sxs-lookup"><span data-stu-id="909a1-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="909a1-132">创建接口</span><span class="sxs-lookup"><span data-stu-id="909a1-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="909a1-133">创建类型等效性接口项目</span><span class="sxs-lookup"><span data-stu-id="909a1-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="909a1-134">在 Visual Studio 中的“文件”菜单上，选择“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="909a1-134">In Visual Studio, on the **File** menu, choose **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="909a1-135">在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。</span><span class="sxs-lookup"><span data-stu-id="909a1-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="909a1-136">在“模板”窗格中，选择“类库”。</span><span class="sxs-lookup"><span data-stu-id="909a1-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="909a1-137">在“名称”框中，键入 `TypeEquivalenceInterface`，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="909a1-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="909a1-138">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="909a1-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="909a1-139">在“解决方案资源管理器”中，右键单击 Class1.cs 文件，然后单击“重命名”。</span><span class="sxs-lookup"><span data-stu-id="909a1-139">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="909a1-140">将文件重命名为 `ISampleInterface.cs`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="909a1-140">Rename the file to `ISampleInterface.cs` and press ENTER.</span></span> <span data-ttu-id="909a1-141">重命名文件也会将类重命名为 `ISampleInterface`。</span><span class="sxs-lookup"><span data-stu-id="909a1-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="909a1-142">此类将表示类的公共接口。</span><span class="sxs-lookup"><span data-stu-id="909a1-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="909a1-143">右键单击 TypeEquivalenceInterface 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="909a1-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="909a1-144">单击“生成”选项卡。</span><span class="sxs-lookup"><span data-stu-id="909a1-144">Click the the **Build** tab.</span></span> <span data-ttu-id="909a1-145">将输出路径设置为开发计算机上的有效位置，例如 `C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="909a1-145">Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="909a1-146">本演练的后续步骤中也将使用此位置。</span><span class="sxs-lookup"><span data-stu-id="909a1-146">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="909a1-147">在编辑项目属性期间，单击“签名”选项卡。</span><span class="sxs-lookup"><span data-stu-id="909a1-147">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="909a1-148">选择“为程序集签名”选项。</span><span class="sxs-lookup"><span data-stu-id="909a1-148">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="909a1-149">在“选择强名称密钥文件”列表中，单击“<新建…>”。</span><span class="sxs-lookup"><span data-stu-id="909a1-149">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="909a1-150">在“密钥文件名”框中，键入 `key.snk`。</span><span class="sxs-lookup"><span data-stu-id="909a1-150">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="909a1-151">清除“使用密码保护密钥文件”复选框。</span><span class="sxs-lookup"><span data-stu-id="909a1-151">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="909a1-152">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="909a1-152">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="909a1-153">打开 ISampleInterface.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="909a1-153">Open the ISampleInterface.cs file.</span></span> <span data-ttu-id="909a1-154">将以下代码添加到 ISampleInterface 类文件，以创建 ISampleInterface 接口。</span><span class="sxs-lookup"><span data-stu-id="909a1-154">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
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
  
7.  <span data-ttu-id="909a1-155">在“工具”菜单上，单击“创建 Guid”。</span><span class="sxs-lookup"><span data-stu-id="909a1-155">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="909a1-156">在“创建 GUID”对话框中，单击“注册表格式”，然后单击“复制”。</span><span class="sxs-lookup"><span data-stu-id="909a1-156">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="909a1-157">单击“退出” 。</span><span class="sxs-lookup"><span data-stu-id="909a1-157">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="909a1-158">在 `Guid` 特性中，删除示例 GUID ，并粘贴从“创建 GUID”对话框复制的 GUID。</span><span class="sxs-lookup"><span data-stu-id="909a1-158">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="909a1-159">删除复制的 GUID 中的大括号 ({})。</span><span class="sxs-lookup"><span data-stu-id="909a1-159">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="909a1-160">在“解决方案资源管理器”中，展开“属性”文件夹。</span><span class="sxs-lookup"><span data-stu-id="909a1-160">In **Solution Explorer**, expand the **Properties** folder.</span></span> <span data-ttu-id="909a1-161">双击 AssemblyInfo.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="909a1-161">Double-click the AssemblyInfo.cs file.</span></span> <span data-ttu-id="909a1-162">向文件中添加以下特性。</span><span class="sxs-lookup"><span data-stu-id="909a1-162">Add the following attribute to the file.</span></span>  
  
    ```csharp  
    [assembly: ImportedFromTypeLib("")]  
    ```  
  
     <span data-ttu-id="909a1-163">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="909a1-163">Save the file.</span></span>  
  
10. <span data-ttu-id="909a1-164">保存项目。</span><span class="sxs-lookup"><span data-stu-id="909a1-164">Save the project.</span></span>  
  
11. <span data-ttu-id="909a1-165">右键单击 TypeEquivalenceInterface 项目，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="909a1-165">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="909a1-166">此时将编译类库 .dll 文件，并保存到指定的生成输出路径中（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="909a1-166">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="909a1-167">创建运行时类</span><span class="sxs-lookup"><span data-stu-id="909a1-167">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="909a1-168">创建类型等效性运行时项目</span><span class="sxs-lookup"><span data-stu-id="909a1-168">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="909a1-169">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="909a1-169">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="909a1-170">在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。</span><span class="sxs-lookup"><span data-stu-id="909a1-170">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="909a1-171">在“模板”窗格中，选择“类库”。</span><span class="sxs-lookup"><span data-stu-id="909a1-171">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="909a1-172">在“名称”框中，键入 `TypeEquivalenceRuntime`，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="909a1-172">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="909a1-173">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="909a1-173">The new project is created.</span></span>  
  
3.  <span data-ttu-id="909a1-174">在“解决方案资源管理器”中，右键单击 Class1.cs 文件，然后单击“重命名”。</span><span class="sxs-lookup"><span data-stu-id="909a1-174">In **Solution Explorer**, right-click the Class1.cs file and click **Rename**.</span></span> <span data-ttu-id="909a1-175">将文件重命名为 `SampleClass.cs`，然后按 Enter。</span><span class="sxs-lookup"><span data-stu-id="909a1-175">Rename the file to `SampleClass.cs` and press ENTER.</span></span> <span data-ttu-id="909a1-176">重命名文件也会将类重命名为 `SampleClass`。</span><span class="sxs-lookup"><span data-stu-id="909a1-176">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="909a1-177">此类将实现 `ISampleInterface` 接口。</span><span class="sxs-lookup"><span data-stu-id="909a1-177">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="909a1-178">右键单击 TypeEquivalenceRuntime 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="909a1-178">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="909a1-179">单击“生成”选项卡。</span><span class="sxs-lookup"><span data-stu-id="909a1-179">Click the **Build** tab.</span></span> <span data-ttu-id="909a1-180">将输出路径设置为 TypeEquivalenceInterface 项目中所用的同一位置，例如，`C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="909a1-180">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="909a1-181">在编辑项目属性期间，单击“签名”选项卡。</span><span class="sxs-lookup"><span data-stu-id="909a1-181">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="909a1-182">选择“为程序集签名”选项。</span><span class="sxs-lookup"><span data-stu-id="909a1-182">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="909a1-183">在“选择强名称密钥文件”列表中，单击“<新建…>”。</span><span class="sxs-lookup"><span data-stu-id="909a1-183">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="909a1-184">在“密钥文件名”框中，键入 `key.snk`。</span><span class="sxs-lookup"><span data-stu-id="909a1-184">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="909a1-185">清除“使用密码保护密钥文件”复选框。</span><span class="sxs-lookup"><span data-stu-id="909a1-185">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="909a1-186">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="909a1-186">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="909a1-187">右键单击 TypeEquivalenceRuntime 项目，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="909a1-187">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="909a1-188">单击“浏览”选项卡，然后浏览到输出路径文件夹。</span><span class="sxs-lookup"><span data-stu-id="909a1-188">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="909a1-189">选择 TypeEquivalenceInterface.dll 文件并单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="909a1-189">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="909a1-190">在“解决方案资源管理器”中，展开“引用”文件夹。</span><span class="sxs-lookup"><span data-stu-id="909a1-190">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="909a1-191">选择 TypeEquivalenceInterface 引用。</span><span class="sxs-lookup"><span data-stu-id="909a1-191">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="909a1-192">在 TypeEquivalenceInterface 引用的“属性”窗口中，将“特定版本”属性设置为“False”。</span><span class="sxs-lookup"><span data-stu-id="909a1-192">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
8.  <span data-ttu-id="909a1-193">将以下代码添加到 SampleClass 类文件，以创建 SampleClass 类。</span><span class="sxs-lookup"><span data-stu-id="909a1-193">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
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
    )  
    ```  
  
9. <span data-ttu-id="909a1-194">保存项目。</span><span class="sxs-lookup"><span data-stu-id="909a1-194">Save the project.</span></span>  
  
10. <span data-ttu-id="909a1-195">右键单击 TypeEquivalenceRuntime 项目，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="909a1-195">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="909a1-196">此时将编译类库 .dll 文件，并保存到指定的生成输出路径中（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="909a1-196">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="909a1-197">创建客户端项目</span><span class="sxs-lookup"><span data-stu-id="909a1-197">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="909a1-198">创建类型等效性客户端项目</span><span class="sxs-lookup"><span data-stu-id="909a1-198">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="909a1-199">在 Visual Studio 中的“文件”菜单上，指向“新建”，然后单击“项目”。</span><span class="sxs-lookup"><span data-stu-id="909a1-199">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="909a1-200">在“新建项目”对话框的“项目类型”窗格中，确保选中“Windows”。</span><span class="sxs-lookup"><span data-stu-id="909a1-200">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="909a1-201">在“模板”窗格中，选择“控制台应用程序”。</span><span class="sxs-lookup"><span data-stu-id="909a1-201">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="909a1-202">在“名称”框中，键入 `TypeEquivalenceClient`，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="909a1-202">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="909a1-203">新项目创建完成。</span><span class="sxs-lookup"><span data-stu-id="909a1-203">The new project is created.</span></span>  
  
3.  <span data-ttu-id="909a1-204">右键单击 TypeEquivalenceClient 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="909a1-204">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="909a1-205">单击“生成”选项卡。</span><span class="sxs-lookup"><span data-stu-id="909a1-205">Click the **Build** tab.</span></span> <span data-ttu-id="909a1-206">将输出路径设置为 TypeEquivalenceInterface 项目中所用的同一位置，例如，`C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="909a1-206">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="909a1-207">右键单击 TypeEquivalenceClient 项目，然后单击“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="909a1-207">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="909a1-208">单击“浏览”选项卡，然后浏览到输出路径文件夹。</span><span class="sxs-lookup"><span data-stu-id="909a1-208">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="909a1-209">选择 TypeEquivalenceInterface.dll 文件（不是 TypeEquivalenceRuntime.dll）并单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="909a1-209">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="909a1-210">在“解决方案资源管理器”中，展开“引用”文件夹。</span><span class="sxs-lookup"><span data-stu-id="909a1-210">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="909a1-211">选择 TypeEquivalenceInterface 引用。</span><span class="sxs-lookup"><span data-stu-id="909a1-211">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="909a1-212">在 TypeEquivalenceInterface 引用的“属性”窗口中，将“嵌入互操作类型”属性设置为“True”。</span><span class="sxs-lookup"><span data-stu-id="909a1-212">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
6.  <span data-ttu-id="909a1-213">将以下代码添加到 Program.cs 文件，以创建客户端程序。</span><span class="sxs-lookup"><span data-stu-id="909a1-213">Add the following code to the Program.cs file to create the client program.</span></span>  
  
    ```csharp  
    using System;  
    using System.Collections.Generic;  
    using System.Linq;  
    using System.Text;  
    using TypeEquivalenceInterface;  
    using System.Reflection;  
  
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
  
7.  <span data-ttu-id="909a1-214">按 Ctrl+F5 生成并运行程序。</span><span class="sxs-lookup"><span data-stu-id="909a1-214">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="909a1-215">修改接口</span><span class="sxs-lookup"><span data-stu-id="909a1-215">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="909a1-216">修改接口</span><span class="sxs-lookup"><span data-stu-id="909a1-216">To modify the interface</span></span>  
  
1.  <span data-ttu-id="909a1-217">在 Visual Studio 中的“文件”菜单上，指向“打开”，然后单击“项目/解决方案”。</span><span class="sxs-lookup"><span data-stu-id="909a1-217">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="909a1-218">在“打开项目”对话框中，右键单击 TypeEquivalenceInterface 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="909a1-218">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="909a1-219">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="909a1-219">Click the **Application** tab.</span></span> <span data-ttu-id="909a1-220">单击“程序集信息”按钮。</span><span class="sxs-lookup"><span data-stu-id="909a1-220">Click the **Assembly Information** button.</span></span> <span data-ttu-id="909a1-221">将“程序集版本”和“文件版本”的值更改为 `2.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="909a1-221">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="909a1-222">打开 SampleInterface.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="909a1-222">Open the SampleInterface.cs file.</span></span> <span data-ttu-id="909a1-223">将以下代码行添加到 ISampleInterface 接口。</span><span class="sxs-lookup"><span data-stu-id="909a1-223">Add the following line of code to the ISampleInterface interface.</span></span>  
  
    ```csharp  
    DateTime GetDate();  
    ```  
  
     <span data-ttu-id="909a1-224">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="909a1-224">Save the file.</span></span>  
  
4.  <span data-ttu-id="909a1-225">保存项目。</span><span class="sxs-lookup"><span data-stu-id="909a1-225">Save the project.</span></span>  
  
5.  <span data-ttu-id="909a1-226">右键单击 TypeEquivalenceInterface 项目，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="909a1-226">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="909a1-227">此时将编译新版本的类库 .dll 文件，并保存到指定的生成输出路径中（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="909a1-227">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="909a1-228">修改运行时类</span><span class="sxs-lookup"><span data-stu-id="909a1-228">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="909a1-229">修改运行时类</span><span class="sxs-lookup"><span data-stu-id="909a1-229">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="909a1-230">在 Visual Studio 中的“文件”菜单上，指向“打开”，然后单击“项目/解决方案”。</span><span class="sxs-lookup"><span data-stu-id="909a1-230">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="909a1-231">在“打开项目”对话框中，右键单击 TypeEquivalenceRuntime 项目，然后单击“属性”。</span><span class="sxs-lookup"><span data-stu-id="909a1-231">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="909a1-232">单击“应用程序”  选项卡。</span><span class="sxs-lookup"><span data-stu-id="909a1-232">Click the **Application** tab.</span></span> <span data-ttu-id="909a1-233">单击“程序集信息”按钮。</span><span class="sxs-lookup"><span data-stu-id="909a1-233">Click the **Assembly Information** button.</span></span> <span data-ttu-id="909a1-234">将“程序集版本”和“文件版本”的值更改为 `2.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="909a1-234">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="909a1-235">打开 SampleClass.cs 文件。</span><span class="sxs-lookup"><span data-stu-id="909a1-235">Open the SampleClass.cs file.</span></span> <span data-ttu-id="909a1-236">将以下代码行添加到 SampleClass 类。</span><span class="sxs-lookup"><span data-stu-id="909a1-236">Add the following lines of code to the SampleClass class.</span></span>  
  
    ```csharp  
    public DateTime GetDate()  
    {  
        return DateTime.Now;  
    }  
    ```  
  
     <span data-ttu-id="909a1-237">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="909a1-237">Save the file.</span></span>  
  
4.  <span data-ttu-id="909a1-238">保存项目。</span><span class="sxs-lookup"><span data-stu-id="909a1-238">Save the project.</span></span>  
  
5.  <span data-ttu-id="909a1-239">右键单击 TypeEquivalenceRuntime 项目，然后单击“生成”。</span><span class="sxs-lookup"><span data-stu-id="909a1-239">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="909a1-240">此时将编译更新版本的类库 .dll 文件，并保存到之前指定的生成输出路径中（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="909a1-240">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="909a1-241">在文件资源管理器中，打开输出路径文件夹（如 C:\TypeEquivalenceSample）。</span><span class="sxs-lookup"><span data-stu-id="909a1-241">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="909a1-242">双击 TypeEquivalenceClient.exe 运行该程序。</span><span class="sxs-lookup"><span data-stu-id="909a1-242">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="909a1-243">程序将反映 TypeEquivalenceRuntime 程序集的未经重新编译的新版本。</span><span class="sxs-lookup"><span data-stu-id="909a1-243">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="909a1-244">请参阅</span><span class="sxs-lookup"><span data-stu-id="909a1-244">See Also</span></span>  
 <span data-ttu-id="909a1-245">[/link（C# 编译器选项）](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="909a1-245">[/link (C# Compiler Options)](../../../../csharp/language-reference/compiler-options/link-compiler-option.md) </span></span>  
 <span data-ttu-id="909a1-246">[C# 编程指南](../../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="909a1-246">[C# Programming Guide](../../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="909a1-247">[使用程序集编程](../../../../framework/app-domains/programming-with-assemblies.md) </span><span class="sxs-lookup"><span data-stu-id="909a1-247">[Programming with Assemblies](../../../../framework/app-domains/programming-with-assemblies.md) </span></span>  
 [<span data-ttu-id="909a1-248">程序集和全局程序集缓存 (C#)</span><span class="sxs-lookup"><span data-stu-id="909a1-248">Assemblies and the Global Assembly Cache (C#)</span></span>](../../../../csharp/programming-guide/concepts/assemblies-gac/index.md)

