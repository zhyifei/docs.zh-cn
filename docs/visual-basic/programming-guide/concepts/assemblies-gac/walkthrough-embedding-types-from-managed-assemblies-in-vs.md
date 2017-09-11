---
title: "演练︰ 嵌入的类型的托管 Visual Studio (Visual Basic 中) 中的程序集 |Microsoft 文档"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: 56ed12ba-adff-4e9c-a668-7fcba80c4795
caps.latest.revision: 3
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: adc58e081cd9b874a841d84b11d92cbffb6ba6b8
ms.contentlocale: zh-cn
ms.lasthandoff: 03/13/2017

---
# <a name="walkthrough-embedding-types-from-managed-assemblies-in-visual-studio-visual-basic"></a><span data-ttu-id="79bc4-102">演练︰ 在 Visual Studio (Visual Basic 中) 中嵌入托管程序集中的类型</span><span class="sxs-lookup"><span data-stu-id="79bc4-102">Walkthrough: Embedding Types from Managed Assemblies in Visual Studio (Visual Basic)</span></span>
<span data-ttu-id="79bc4-103">如果您嵌入类型信息从强名称的托管程序集，可以松耦合应用程序以实现版本独立性中的类型。</span><span class="sxs-lookup"><span data-stu-id="79bc4-103">If you embed type information from a strong-named managed assembly, you can loosely couple types in an application to achieve version independence.</span></span> <span data-ttu-id="79bc4-104">也就是说，您的程序可以编写为使用多个版本中的类型的托管库，而无需为每个版本重新编译。</span><span class="sxs-lookup"><span data-stu-id="79bc4-104">That is, your program can be written to use types from multiple versions of a managed library without having to be recompiled for each version.</span></span>  
  
 <span data-ttu-id="79bc4-105">用 COM 互操作，例如从 Microsoft Office 中使用自动化对象的应用程序经常使用嵌入类型。</span><span class="sxs-lookup"><span data-stu-id="79bc4-105">Type embedding is frequently used with COM interop, such as an application that uses automation objects from Microsoft Office.</span></span> <span data-ttu-id="79bc4-106">嵌入类型信息，使程序可以使用不同版本的 Microsoft Office 的不同计算机上的相同内部版本。</span><span class="sxs-lookup"><span data-stu-id="79bc4-106">Embedding type information enables the same build of a program to work with different versions of Microsoft Office on different computers.</span></span> <span data-ttu-id="79bc4-107">但是，您还可以使用嵌入了一个完全托管的解决方案的类型。</span><span class="sxs-lookup"><span data-stu-id="79bc4-107">However, you can also use type embedding with a fully managed solution.</span></span>  
  
 <span data-ttu-id="79bc4-108">可以从具有以下特征的程序集嵌入类型信息︰</span><span class="sxs-lookup"><span data-stu-id="79bc4-108">Type information can be embedded from an assembly that has the following characteristics:</span></span>  
  
-   <span data-ttu-id="79bc4-109">程序集公开至少一个公共接口。</span><span class="sxs-lookup"><span data-stu-id="79bc4-109">The assembly exposes at least one public interface.</span></span>  
  
-   <span data-ttu-id="79bc4-110">表示嵌入的接口为`ComImport`属性和一个`Guid`属性 （和一个唯一的 GUID）。</span><span class="sxs-lookup"><span data-stu-id="79bc4-110">The embedded interfaces are annotated with a `ComImport` attribute and a `Guid` attribute (and a unique GUID).</span></span>  
  
-   <span data-ttu-id="79bc4-111">程序集通过批注`ImportedFromTypeLib`属性或`PrimaryInteropAssembly`属性和程序集级别`Guid`属性。</span><span class="sxs-lookup"><span data-stu-id="79bc4-111">The assembly is annotated with the `ImportedFromTypeLib` attribute or the `PrimaryInteropAssembly` attribute, and an assembly-level `Guid` attribute.</span></span> <span data-ttu-id="79bc4-112">(默认情况下，Visual Basic 项目模板包含程序集级别`Guid`属性。)</span><span class="sxs-lookup"><span data-stu-id="79bc4-112">(By default, Visual Basic project templates include an assembly-level `Guid` attribute.)</span></span>  
  
 <span data-ttu-id="79bc4-113">指定可嵌入的公共接口后，您可以创建实现这些接口的运行时类。</span><span class="sxs-lookup"><span data-stu-id="79bc4-113">After you have specified the public interfaces that can be embedded, you can create runtime classes that implement those interfaces.</span></span> <span data-ttu-id="79bc4-114">客户端程序然后可以通过引用包含的公共接口和设置的程序集嵌入在设计时这些接口的类型信息`Embed Interop Types`属性的引用的`True`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-114">A client program can then embed the type information for those interfaces at design time by referencing the assembly that contains the public interfaces and setting the `Embed Interop Types` property of the reference to `True`.</span></span> <span data-ttu-id="79bc4-115">这相当于使用命令行编译器，使用引用的程序集`/link`编译器选项。</span><span class="sxs-lookup"><span data-stu-id="79bc4-115">This is equivalent to using the command line compiler and referencing the assembly by using the `/link` compiler option.</span></span> <span data-ttu-id="79bc4-116">然后，客户端程序可以加载运行时对象类型化为这些接口的实例。</span><span class="sxs-lookup"><span data-stu-id="79bc4-116">The client program can then load instances of your runtime objects typed as those interfaces.</span></span> <span data-ttu-id="79bc4-117">如果您创建具有强名称的运行时程序集的新版本，客户端程序不必使用更新的运行时的程序集重新编译。</span><span class="sxs-lookup"><span data-stu-id="79bc4-117">If you create a new version of your strong-named runtime assembly, the client program does not have to be recompiled with the updated runtime assembly.</span></span> <span data-ttu-id="79bc4-118">相反，客户端程序将继续使用任何版本的运行时程序集是提供给它，将用于公共接口的嵌入的类型信息。</span><span class="sxs-lookup"><span data-stu-id="79bc4-118">Instead, the client program continues to use whichever version of the runtime assembly is available to it, using the embedded type information for the public interfaces.</span></span>  
  
 <span data-ttu-id="79bc4-119">由于类型嵌入的主要功能是支持嵌入类型信息从 COM 互操作程序集，以下限制将适用时完全托管的解决方案中嵌入类型信息︰</span><span class="sxs-lookup"><span data-stu-id="79bc4-119">Because the primary function of type embedding is to support embedding of type information from COM interop assemblies, the following limitations apply when you embed type information in a fully managed solution:</span></span>  
  
-   <span data-ttu-id="79bc4-120">嵌入只有特定于 COM 互操作的属性;其他属性将被忽略。</span><span class="sxs-lookup"><span data-stu-id="79bc4-120">Only attributes specific to COM interop are embedded; other attributes are ignored.</span></span>  
  
-   <span data-ttu-id="79bc4-121">如果某个类型使用的泛型参数的泛型参数的类型为嵌入的类型，不能跨程序集边界使用该类型。</span><span class="sxs-lookup"><span data-stu-id="79bc4-121">If a type uses generic parameters and the type of the generic parameter is an embedded type, that type cannot be used across an assembly boundary.</span></span> <span data-ttu-id="79bc4-122">跨程序集边界的示例包括从另一个程序集调用方法或其他程序集中派生类型从一种类型定义。</span><span class="sxs-lookup"><span data-stu-id="79bc4-122">Examples of crossing an assembly boundary include calling a method from another assembly or a deriving a type from a type defined in another assembly.</span></span>  
  
-   <span data-ttu-id="79bc4-123">未嵌入常量。</span><span class="sxs-lookup"><span data-stu-id="79bc4-123">Constants are not embedded.</span></span>  
  
-   <span data-ttu-id="79bc4-124"><xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName>类不支持嵌入的类型作为密钥。</xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="79bc4-124">The <xref:System.Collections.Generic.Dictionary%602?displayProperty=fullName> class does not support an embedded type as a key.</span></span> <span data-ttu-id="79bc4-125">您可以实现您自己的字典类型以支持嵌入的类型作为密钥。</span><span class="sxs-lookup"><span data-stu-id="79bc4-125">You can implement your own dictionary type to support an embedded type as a key.</span></span>  
  
 <span data-ttu-id="79bc4-126">在本演练中，将执行以下操作︰</span><span class="sxs-lookup"><span data-stu-id="79bc4-126">In this walkthrough, you will do the following:</span></span>  
  
-   <span data-ttu-id="79bc4-127">创建具有强名称程序集具有一个公共接口，其中包含可嵌入类型信息。</span><span class="sxs-lookup"><span data-stu-id="79bc4-127">Create a strong-named assembly that has a public interface that contains type information that can be embedded.</span></span>  
  
-   <span data-ttu-id="79bc4-128">创建具有强名称的运行时程序集实现该公共接口。</span><span class="sxs-lookup"><span data-stu-id="79bc4-128">Create a strong-named runtime assembly that implements that public interface.</span></span>  
  
-   <span data-ttu-id="79bc4-129">创建嵌入的公共接口的类型信息，并创建运行时程序集中类的实例的客户端程序。</span><span class="sxs-lookup"><span data-stu-id="79bc4-129">Create a client program that embeds the type information from the public interface and creates an instance of the class from the runtime assembly.</span></span>  
  
-   <span data-ttu-id="79bc4-130">修改并重新生成运行时程序集。</span><span class="sxs-lookup"><span data-stu-id="79bc4-130">Modify and rebuild the runtime assembly.</span></span>  
  
-   <span data-ttu-id="79bc4-131">运行客户端程序运行时程序集的新版本正在使用而无需重新编译客户端程序。</span><span class="sxs-lookup"><span data-stu-id="79bc4-131">Run the client program to see that the new version of the runtime assembly is being used without having to recompile the client program.</span></span>  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="creating-an-interface"></a><span data-ttu-id="79bc4-132">创建一个接口</span><span class="sxs-lookup"><span data-stu-id="79bc4-132">Creating an Interface</span></span>  
  
#### <a name="to-create-the-type-equivalence-interface-project"></a><span data-ttu-id="79bc4-133">若要创建类型等效性接口项目</span><span class="sxs-lookup"><span data-stu-id="79bc4-133">To create the type equivalence interface project</span></span>  
  
1.  <span data-ttu-id="79bc4-134">在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-134">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="79bc4-135">在**新项目**对话框中，在**项目类型**窗格中，请确保**Windows**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="79bc4-135">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="79bc4-136">选择**类库**中**模板**窗格。</span><span class="sxs-lookup"><span data-stu-id="79bc4-136">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="79bc4-137">在**名称**框中，键入`TypeEquivalenceInterface`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-137">In the **Name** box, type `TypeEquivalenceInterface`, and then click **OK**.</span></span> <span data-ttu-id="79bc4-138">创建新项目。</span><span class="sxs-lookup"><span data-stu-id="79bc4-138">The new project is created.</span></span>  
  
3.  <span data-ttu-id="79bc4-139">在**解决方案资源管理器**，用鼠标右键单击 Class1.vb 文件，然后单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-139">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="79bc4-140">文件重命名为`ISampleInterface.vb`，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="79bc4-140">Rename the file to `ISampleInterface.vb` and press ENTER.</span></span> <span data-ttu-id="79bc4-141">重命名该文件也进行重命名为该类`ISampleInterface`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-141">Renaming the file will also rename the class to `ISampleInterface`.</span></span> <span data-ttu-id="79bc4-142">此类将表示为类的公共接口。</span><span class="sxs-lookup"><span data-stu-id="79bc4-142">This class will represent the public interface for the class.</span></span>  
  
4.  <span data-ttu-id="79bc4-143">右击 TypeEquivalenceInterface 项目并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-143">Right-click the TypeEquivalenceInterface project and click **Properties**.</span></span> <span data-ttu-id="79bc4-144">单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="79bc4-144">Click the **Compile** tab.</span></span> <span data-ttu-id="79bc4-145">输出路径设置为您的开发计算机上的有效位置如`C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-145">Set the output path to a valid location on your development computer, such as `C:\TypeEquivalenceSample`.</span></span> <span data-ttu-id="79bc4-146">此外将在本演练中稍后的步骤中使用此位置。</span><span class="sxs-lookup"><span data-stu-id="79bc4-146">This location will also be used in a later step in this walkthrough.</span></span>  
  
5.  <span data-ttu-id="79bc4-147">在仍在编辑项目属性，同时单击**签名**选项卡。</span><span class="sxs-lookup"><span data-stu-id="79bc4-147">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="79bc4-148">选择**为程序集签名**选项。</span><span class="sxs-lookup"><span data-stu-id="79bc4-148">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="79bc4-149">在**选择强名称密钥文件**列表中，单击** <New...> **。</New...></span><span class="sxs-lookup"><span data-stu-id="79bc4-149">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="79bc4-150">在**密钥文件名称**框中，键入`key.snk`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-150">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="79bc4-151">清除**保护密钥文件使用的密码**复选框。</span><span class="sxs-lookup"><span data-stu-id="79bc4-151">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="79bc4-152">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-152">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="79bc4-153">打开 ISampleInterface.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="79bc4-153">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="79bc4-154">将以下代码添加到 ISampleInterface 类文件以创建 ISampleInterface 界面。</span><span class="sxs-lookup"><span data-stu-id="79bc4-154">Add the following code to the ISampleInterface class file to create the ISampleInterface interface.</span></span>  
  
<span data-ttu-id="79bc4-155"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="79bc4-155"><CodeContentPlaceHolder>0</CodeContentPlaceHolder></span></span>  
7.  <span data-ttu-id="79bc4-156">在**工具**菜单上，单击**创建 Guid**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-156">On the **Tools** menu, click **Create Guid**.</span></span> <span data-ttu-id="79bc4-157">在**创建 GUID**对话框中，单击**注册表格式**，然后单击**副本**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-157">In the **Create GUID** dialog box, click **Registry Format** and then click **Copy**.</span></span> <span data-ttu-id="79bc4-158">单击“退出” ****。</span><span class="sxs-lookup"><span data-stu-id="79bc4-158">Click **Exit**.</span></span>  
  
8.  <span data-ttu-id="79bc4-159">在`Guid`属性，删除样本 GUID 并粘贴从复制的 GUID**创建 GUID**对话框。</span><span class="sxs-lookup"><span data-stu-id="79bc4-159">In the `Guid` attribute, delete the sample GUID and paste in the GUID that you copied from the **Create GUID** dialog box.</span></span> <span data-ttu-id="79bc4-160">从复制的 GUID 中删除大括号 （{}）。</span><span class="sxs-lookup"><span data-stu-id="79bc4-160">Remove the braces ({}) from the copied GUID.</span></span>  
  
9. <span data-ttu-id="79bc4-161">在**项目**菜单上，单击**显示所有文件**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-161">On the **Project** menu, click **Show All Files**.</span></span>  
  
10. <span data-ttu-id="79bc4-162">在**解决方案资源管理器**，展开**我的项目**文件夹。</span><span class="sxs-lookup"><span data-stu-id="79bc4-162">In **Solution Explorer**, expand the **My Project** folder.</span></span> <span data-ttu-id="79bc4-163">双击 AssemblyInfo.vb。</span><span class="sxs-lookup"><span data-stu-id="79bc4-163">Double-click the AssemblyInfo.vb.</span></span> <span data-ttu-id="79bc4-164">将以下属性添加到该文件。</span><span class="sxs-lookup"><span data-stu-id="79bc4-164">Add the following attribute to the file.</span></span>  
  
<span data-ttu-id="79bc4-165"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="79bc4-165"><CodeContentPlaceHolder>1</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="79bc4-166">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="79bc4-166">Save the file.</span></span>  
  
11. <span data-ttu-id="79bc4-167">保存项目。</span><span class="sxs-lookup"><span data-stu-id="79bc4-167">Save the project.</span></span>  
  
12. <span data-ttu-id="79bc4-168">右击 TypeEquivalenceInterface 项目并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-168">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="79bc4-169">编译和保存到指定的生成输出路径 (例如，C:\TypeEquivalenceSample) 类库.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="79bc4-169">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-runtime-class"></a><span data-ttu-id="79bc4-170">创建运行时类</span><span class="sxs-lookup"><span data-stu-id="79bc4-170">Creating a Runtime Class</span></span>  
  
#### <a name="to-create-the-type-equivalence-runtime-project"></a><span data-ttu-id="79bc4-171">若要创建类型等效性运行时项目</span><span class="sxs-lookup"><span data-stu-id="79bc4-171">To create the type equivalence runtime project</span></span>  
  
1.  <span data-ttu-id="79bc4-172">在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-172">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="79bc4-173">在**新项目**对话框中，在**项目类型**窗格中，请确保**Windows**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="79bc4-173">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="79bc4-174">选择**类库**中**模板**窗格。</span><span class="sxs-lookup"><span data-stu-id="79bc4-174">Select **Class Library** in the **Templates** pane.</span></span> <span data-ttu-id="79bc4-175">在**名称**框中，键入`TypeEquivalenceRuntime`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-175">In the **Name** box, type `TypeEquivalenceRuntime`, and then click **OK**.</span></span> <span data-ttu-id="79bc4-176">创建新项目。</span><span class="sxs-lookup"><span data-stu-id="79bc4-176">The new project is created.</span></span>  
  
3.  <span data-ttu-id="79bc4-177">在**解决方案资源管理器**，用鼠标右键单击 Class1.vb 文件，然后单击**重命名**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-177">In **Solution Explorer**, right-click the Class1.vb file and click **Rename**.</span></span> <span data-ttu-id="79bc4-178">文件重命名为`SampleClass.vb`，然后按 enter 键。</span><span class="sxs-lookup"><span data-stu-id="79bc4-178">Rename the file to `SampleClass.vb` and press ENTER.</span></span> <span data-ttu-id="79bc4-179">此外会重命名该文件重命名为该类`SampleClass`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-179">Renaming the file also renames the class to `SampleClass`.</span></span> <span data-ttu-id="79bc4-180">此类将实现`ISampleInterface`接口。</span><span class="sxs-lookup"><span data-stu-id="79bc4-180">This class will implement the `ISampleInterface` interface.</span></span>  
  
4.  <span data-ttu-id="79bc4-181">右击 TypeEquivalenceRuntime 项目并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-181">Right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="79bc4-182">单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="79bc4-182">Click the **Compile** tab.</span></span> <span data-ttu-id="79bc4-183">将输出路径设置到相同的位置在 TypeEquivalenceInterface 项目中，例如，使用`C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-183">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
5.  <span data-ttu-id="79bc4-184">在仍在编辑项目属性，同时单击**签名**选项卡。</span><span class="sxs-lookup"><span data-stu-id="79bc4-184">While still editing the project properties, click the **Signing** tab.</span></span> <span data-ttu-id="79bc4-185">选择**为程序集签名**选项。</span><span class="sxs-lookup"><span data-stu-id="79bc4-185">Select the **Sign the assembly** option.</span></span> <span data-ttu-id="79bc4-186">在**选择强名称密钥文件**列表中，单击** <New...> **。</New...></span><span class="sxs-lookup"><span data-stu-id="79bc4-186">In the **Choose a strong name key file** list, click **<New...>**.</span></span> <span data-ttu-id="79bc4-187">在**密钥文件名称**框中，键入`key.snk`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-187">In the **Key file name** box, type `key.snk`.</span></span> <span data-ttu-id="79bc4-188">清除**保护密钥文件使用的密码**复选框。</span><span class="sxs-lookup"><span data-stu-id="79bc4-188">Clear the **Protect my key file with a password** check box.</span></span> <span data-ttu-id="79bc4-189">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-189">Click **OK**.</span></span>  
  
6.  <span data-ttu-id="79bc4-190">右击 TypeEquivalenceRuntime 项目并单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-190">Right-click the TypeEquivalenceRuntime project and click **Add Reference**.</span></span> <span data-ttu-id="79bc4-191">单击**浏览**选项卡上，浏览到输出路径文件夹。</span><span class="sxs-lookup"><span data-stu-id="79bc4-191">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="79bc4-192">选择 TypeEquivalenceInterface.dll 文件并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-192">Select the TypeEquivalenceInterface.dll file and click **OK**.</span></span>  
  
7.  <span data-ttu-id="79bc4-193">在**项目**菜单上，单击**显示所有文件**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-193">On the **Project** menu, click **Show All Files**.</span></span>  
  
8.  <span data-ttu-id="79bc4-194">在**解决方案资源管理器**，展开**引用**文件夹。</span><span class="sxs-lookup"><span data-stu-id="79bc4-194">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="79bc4-195">选择 TypeEquivalenceInterface 引用。</span><span class="sxs-lookup"><span data-stu-id="79bc4-195">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="79bc4-196">在有关 TypeEquivalenceInterface 参考属性窗口中，设置**特定版本**属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-196">In the Properties window for the TypeEquivalenceInterface reference, set the **Specific Version** property to **False**.</span></span>  
  
9. <span data-ttu-id="79bc4-197">将以下代码添加到 SampleClass 类文件以创建 SampleClass 类。</span><span class="sxs-lookup"><span data-stu-id="79bc4-197">Add the following code to the SampleClass class file to create the SampleClass class.</span></span>  
  
<span data-ttu-id="79bc4-198"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="79bc4-198"><CodeContentPlaceHolder>2</CodeContentPlaceHolder></span></span>  
10. <span data-ttu-id="79bc4-199">保存项目。</span><span class="sxs-lookup"><span data-stu-id="79bc4-199">Save the project.</span></span>  
  
11. <span data-ttu-id="79bc4-200">右击 TypeEquivalenceRuntime 项目并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-200">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="79bc4-201">编译和保存到指定的生成输出路径 (例如，C:\TypeEquivalenceSample) 类库.dll 文件。</span><span class="sxs-lookup"><span data-stu-id="79bc4-201">The class library .dll file is compiled and saved to the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="creating-a-client-project"></a><span data-ttu-id="79bc4-202">创建客户端项目</span><span class="sxs-lookup"><span data-stu-id="79bc4-202">Creating a Client Project</span></span>  
  
#### <a name="to-create-the-type-equivalence-client-project"></a><span data-ttu-id="79bc4-203">若要创建类型等效性客户端项目</span><span class="sxs-lookup"><span data-stu-id="79bc4-203">To create the type equivalence client project</span></span>  
  
1.  <span data-ttu-id="79bc4-204">在 Visual Studio 中，在**文件**菜单上，指向**新建**，然后单击**项目**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-204">In Visual Studio, on the **File** menu, point to **New** and then click **Project**.</span></span>  
  
2.  <span data-ttu-id="79bc4-205">在**新项目**对话框中，在**项目类型**窗格中，请确保**Windows**处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="79bc4-205">In the **New Project** dialog box, in the **Project Types** pane, make sure that **Windows** is selected.</span></span> <span data-ttu-id="79bc4-206">选择**控制台应用程序**中**模板**窗格。</span><span class="sxs-lookup"><span data-stu-id="79bc4-206">Select **Console Application** in the **Templates** pane.</span></span> <span data-ttu-id="79bc4-207">在**名称**框中，键入`TypeEquivalenceClient`，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-207">In the **Name** box, type `TypeEquivalenceClient`, and then click **OK**.</span></span> <span data-ttu-id="79bc4-208">创建新项目。</span><span class="sxs-lookup"><span data-stu-id="79bc4-208">The new project is created.</span></span>  
  
3.  <span data-ttu-id="79bc4-209">右击 TypeEquivalenceClient 项目并单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-209">Right-click the TypeEquivalenceClient project and click **Properties**.</span></span> <span data-ttu-id="79bc4-210">单击“编译”****选项卡。</span><span class="sxs-lookup"><span data-stu-id="79bc4-210">Click the **Compile** tab.</span></span> <span data-ttu-id="79bc4-211">将输出路径设置到相同的位置在 TypeEquivalenceInterface 项目中，例如，使用`C:\TypeEquivalenceSample`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-211">Set the output path to the same location you used in the TypeEquivalenceInterface project, for example, `C:\TypeEquivalenceSample`.</span></span>  
  
4.  <span data-ttu-id="79bc4-212">右击 TypeEquivalenceClient 项目并单击**添加引用**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-212">Right-click the TypeEquivalenceClient project and click **Add Reference**.</span></span> <span data-ttu-id="79bc4-213">单击**浏览**选项卡上，浏览到输出路径文件夹。</span><span class="sxs-lookup"><span data-stu-id="79bc4-213">Click the **Browse** tab and browse to the output path folder.</span></span> <span data-ttu-id="79bc4-214">选择 TypeEquivalenceInterface.dll 文件 (不 TypeEquivalenceRuntime.dll) 并单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-214">Select the TypeEquivalenceInterface.dll file (not the TypeEquivalenceRuntime.dll) and click **OK**.</span></span>  
  
5.  <span data-ttu-id="79bc4-215">在**项目**菜单上，单击**显示所有文件**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-215">On the **Project** menu, click **Show All Files**.</span></span>  
  
6.  <span data-ttu-id="79bc4-216">在**解决方案资源管理器**，展开**引用**文件夹。</span><span class="sxs-lookup"><span data-stu-id="79bc4-216">In **Solution Explorer**, expand the **References** folder.</span></span> <span data-ttu-id="79bc4-217">选择 TypeEquivalenceInterface 引用。</span><span class="sxs-lookup"><span data-stu-id="79bc4-217">Select the TypeEquivalenceInterface reference.</span></span> <span data-ttu-id="79bc4-218">在有关 TypeEquivalenceInterface 参考属性窗口中，设置**嵌入互操作类型**属性设置为**True**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-218">In the Properties window for the TypeEquivalenceInterface reference, set the **Embed Interop Types** property to **True**.</span></span>  
  
7.  <span data-ttu-id="79bc4-219">将以下代码添加到 Module1.vb 文件以创建客户端程序。</span><span class="sxs-lookup"><span data-stu-id="79bc4-219">Add the following code to the Module1.vb file to create the client program.</span></span>  
  
<span data-ttu-id="79bc4-220"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="79bc4-220"><CodeContentPlaceHolder>3</CodeContentPlaceHolder></span></span>  
8.  <span data-ttu-id="79bc4-221">按 CTRL + F5 生成并运行该程序。</span><span class="sxs-lookup"><span data-stu-id="79bc4-221">Press CTRL+F5 to build and run the program.</span></span>  
  
## <a name="modifying-the-interface"></a><span data-ttu-id="79bc4-222">修改界面</span><span class="sxs-lookup"><span data-stu-id="79bc4-222">Modifying the Interface</span></span>  
  
#### <a name="to-modify-the-interface"></a><span data-ttu-id="79bc4-223">若要修改的界面</span><span class="sxs-lookup"><span data-stu-id="79bc4-223">To modify the interface</span></span>  
  
1.  <span data-ttu-id="79bc4-224">在 Visual Studio 中，在**文件**菜单上，指向**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-224">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="79bc4-225">在**打开项目**对话框中，右键单击 TypeEquivalenceInterface 项目，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-225">In the **Open Project** dialog box, right-click the TypeEquivalenceInterface project, and then click **Properties**.</span></span> <span data-ttu-id="79bc4-226">单击“应用程序” **** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="79bc4-226">Click the **Application** tab.</span></span> <span data-ttu-id="79bc4-227">单击**程序集信息**按钮。</span><span class="sxs-lookup"><span data-stu-id="79bc4-227">Click the **Assembly Information** button.</span></span> <span data-ttu-id="79bc4-228">更改**程序集版本**和**文件版本**值复制到`2.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-228">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="79bc4-229">打开 ISampleInterface.vb 文件。</span><span class="sxs-lookup"><span data-stu-id="79bc4-229">Open the ISampleInterface.vb file.</span></span> <span data-ttu-id="79bc4-230">将下面的代码行添加到 ISampleInterface 接口。</span><span class="sxs-lookup"><span data-stu-id="79bc4-230">Add the following line of code to the ISampleInterface interface.</span></span>  
  
<span data-ttu-id="79bc4-231"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span><span class="sxs-lookup"><span data-stu-id="79bc4-231"><CodeContentPlaceHolder>4</CodeContentPlaceHolder></span></span>  
     <span data-ttu-id="79bc4-232">保存该文件。</span><span class="sxs-lookup"><span data-stu-id="79bc4-232">Save the file.</span></span>  
  
4.  <span data-ttu-id="79bc4-233">保存项目。</span><span class="sxs-lookup"><span data-stu-id="79bc4-233">Save the project.</span></span>  
  
5.  <span data-ttu-id="79bc4-234">右击 TypeEquivalenceInterface 项目并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-234">Right-click the TypeEquivalenceInterface project and click **Build**.</span></span> <span data-ttu-id="79bc4-235">编译和保存在指定的生成输出路径 (例如，C:\TypeEquivalenceSample) 类库.dll 文件的新版本。</span><span class="sxs-lookup"><span data-stu-id="79bc4-235">A new version of the class library .dll file is compiled and saved in the specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
## <a name="modifying-the-runtime-class"></a><span data-ttu-id="79bc4-236">修改运行时类</span><span class="sxs-lookup"><span data-stu-id="79bc4-236">Modifying the Runtime Class</span></span>  
  
#### <a name="to-modify-the-runtime-class"></a><span data-ttu-id="79bc4-237">若要修改的运行时类</span><span class="sxs-lookup"><span data-stu-id="79bc4-237">To modify the runtime class</span></span>  
  
1.  <span data-ttu-id="79bc4-238">在 Visual Studio 中，在**文件**菜单上，指向**打开**，然后单击**项目/解决方案**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-238">In Visual Studio, on the **File** menu, point to **Open**, and then click **Project/Solution**.</span></span>  
  
2.  <span data-ttu-id="79bc4-239">在**打开项目**对话框框中，右击 TypeEquivalenceRuntime 项目，单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-239">In the **Open Project** dialog box, right-click the TypeEquivalenceRuntime project and click **Properties**.</span></span> <span data-ttu-id="79bc4-240">单击“应用程序” **** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="79bc4-240">Click the **Application** tab.</span></span> <span data-ttu-id="79bc4-241">单击**程序集信息**按钮。</span><span class="sxs-lookup"><span data-stu-id="79bc4-241">Click the **Assembly Information** button.</span></span> <span data-ttu-id="79bc4-242">更改**程序集版本**和**文件版本**值复制到`2.0.0.0`。</span><span class="sxs-lookup"><span data-stu-id="79bc4-242">Change the **Assembly Version** and **File Version** values to `2.0.0.0`.</span></span>  
  
3.  <span data-ttu-id="79bc4-243">打开 SampleClass.vbfile。</span><span class="sxs-lookup"><span data-stu-id="79bc4-243">Open the SampleClass.vbfile.</span></span> <span data-ttu-id="79bc4-244">将下面的代码行添加到 SampleClass 类。</span><span class="sxs-lookup"><span data-stu-id="79bc4-244">Add the following lines of code to the SampleClass class.</span></span>  
  
```vb  
Public Function GetDate() As DateTime Implements ISampleInterface.GetDate  
    Return Now  
End Function  
```  
  
     Save the file.  
  
4.  <span data-ttu-id="79bc4-245">保存项目。</span><span class="sxs-lookup"><span data-stu-id="79bc4-245">Save the project.</span></span>  
  
5.  <span data-ttu-id="79bc4-246">右击 TypeEquivalenceRuntime 项目并单击**生成**。</span><span class="sxs-lookup"><span data-stu-id="79bc4-246">Right-click the TypeEquivalenceRuntime project and click **Build**.</span></span> <span data-ttu-id="79bc4-247">编译和保存在以前指定的生成输出路径 (例如，C:\TypeEquivalenceSample) 类库.dll 文件的更新的版本。</span><span class="sxs-lookup"><span data-stu-id="79bc4-247">An updated version of the class library .dll file is compiled and saved in the previously specified build output path (for example, C:\TypeEquivalenceSample).</span></span>  
  
6.  <span data-ttu-id="79bc4-248">在文件资源管理器中，打开输出路径文件夹 (例如，C:\TypeEquivalenceSample)。</span><span class="sxs-lookup"><span data-stu-id="79bc4-248">In File Explorer, open the output path folder (for example, C:\TypeEquivalenceSample).</span></span> <span data-ttu-id="79bc4-249">双击 TypeEquivalenceClient.exe 以运行该程序。</span><span class="sxs-lookup"><span data-stu-id="79bc4-249">Double-click the TypeEquivalenceClient.exe to run the program.</span></span> <span data-ttu-id="79bc4-250">该程序将反映 TypeEquivalenceRuntime 程序集的新版本，而不具有已重新编译。</span><span class="sxs-lookup"><span data-stu-id="79bc4-250">The program will reflect the new version of the TypeEquivalenceRuntime assembly without having been recompiled.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79bc4-251">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79bc4-251">See Also</span></span>  
 <span data-ttu-id="79bc4-252">[/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md) </span><span class="sxs-lookup"><span data-stu-id="79bc4-252">[/link (Visual Basic)](../../../../visual-basic/reference/command-line-compiler/link.md) </span></span>  
<span data-ttu-id="79bc4-253"> [编程概念](../../../../visual-basic/programming-guide/concepts/index.md) </span><span class="sxs-lookup"><span data-stu-id="79bc4-253"> [Programming Concepts](../../../../visual-basic/programming-guide/concepts/index.md) </span></span>  
<span data-ttu-id="79bc4-254"> [使用程序集编程](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6) </span><span class="sxs-lookup"><span data-stu-id="79bc4-254"> [Programming with Assemblies](http://msdn.microsoft.com/library/25918b15-701d-42c7-95fc-c290d08648d6) </span></span>  
<span data-ttu-id="79bc4-255"> [程序集和全局程序集缓存 (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span><span class="sxs-lookup"><span data-stu-id="79bc4-255"> [Assemblies and the Global Assembly Cache (Visual Basic)](../../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)</span></span>

