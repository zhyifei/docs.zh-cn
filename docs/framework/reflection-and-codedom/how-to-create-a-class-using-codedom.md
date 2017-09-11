---
title: "如何：使用 CodeDOM 创建类"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Code Document Object Model, graphs
- Code Document Object Model, creating classes
- graphing with CodeDOM
- CodeDOM, creating classes
- CodeDOM, graphs
ms.assetid: 0ceb70fe-36e1-49bb-922b-e9f615c20a14
caps.latest.revision: 10
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 3876ed881d98b4ee0bdb66f43de3de939111d45d
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-create-a-class-using-codedom"></a><span data-ttu-id="34e45-102">如何：使用 CodeDOM 创建类</span><span class="sxs-lookup"><span data-stu-id="34e45-102">How to: Create a Class Using CodeDOM</span></span>
<span data-ttu-id="34e45-103">以下过程说明如何创建和编译 CodeDOM 图，此图会生成包含以下各项的类：两个字段、三个属性、一个方法、一个构造函数和一个入口点。</span><span class="sxs-lookup"><span data-stu-id="34e45-103">The following procedures illustrate how to create and compile a CodeDOM graph that generates a class containing two fields, three properties, a method, a constructor, and an entry point.</span></span>  
  
1.  <span data-ttu-id="34e45-104">创建将使用 CodeDOM 代码生成类的源代码的控制台应用程序。</span><span class="sxs-lookup"><span data-stu-id="34e45-104">Create a console application that will use CodeDOM code to generate the source code for a class.</span></span>  
  
     <span data-ttu-id="34e45-105">在此示例中，生成类命名为 `Sample`，生成的代码是名为 SampleCode 的文件中的一个名为 `CodeDOMCreatedClass` 的类。</span><span class="sxs-lookup"><span data-stu-id="34e45-105">In this example, the generating class is named `Sample`, and the generated code is a class named `CodeDOMCreatedClass` in a file named SampleCode.</span></span>  
  
2.  <span data-ttu-id="34e45-106">在生成类中，初始化 CodeDOM 图，并使用 CodeDOM 方法定义生成类的成员、构造函数和入口点（`Main` 方法）。</span><span class="sxs-lookup"><span data-stu-id="34e45-106">In the generating class, initialize the CodeDOM graph and use CodeDOM methods to define the members, constructor, and entry point (`Main` method) of the generated class.</span></span>  
  
     <span data-ttu-id="34e45-107">在此示例中，生成类包含两个字段、三个属性、一个构造函数、一个方法和一个 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="34e45-107">In this example, the generated class has two fields, three properties, a constructor, a method, and a `Main` method.</span></span>  
  
3.  <span data-ttu-id="34e45-108">在生成类中，创建一个语言特定代码提供程序，并调用其 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 方法从该图生成代码。</span><span class="sxs-lookup"><span data-stu-id="34e45-108">In the generating class, create a language-specific code provider and call its <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method to generate the code from the graph.</span></span>  
  
4.  <span data-ttu-id="34e45-109">编译并执行应用程序以生成代码。</span><span class="sxs-lookup"><span data-stu-id="34e45-109">Compile and execute the application to generate the code.</span></span>  
  
     <span data-ttu-id="34e45-110">在此示例中，生成的代码位于名为 SampleCode 的文件中。</span><span class="sxs-lookup"><span data-stu-id="34e45-110">In this example, the generated code is in a file named SampleCode.</span></span> <span data-ttu-id="34e45-111">编译并执行此代码以查看样本输出。</span><span class="sxs-lookup"><span data-stu-id="34e45-111">Compile and execute that code to see the sample output.</span></span>  
  
### <a name="to-create-the-application-that-will-execute-the-codedom-code"></a><span data-ttu-id="34e45-112">创建将执行 CodeDOM 代码的应用程序</span><span class="sxs-lookup"><span data-stu-id="34e45-112">To create the application that will execute the CodeDOM code</span></span>  
  
-   <span data-ttu-id="34e45-113">创建要包含 CodeDOM 代码的控制台应用程序类。</span><span class="sxs-lookup"><span data-stu-id="34e45-113">Create a console application class to contain the CodeDOM code.</span></span> <span data-ttu-id="34e45-114">定义要在该类中使用的全局字段，以便引用程序集 (<xref:System.CodeDom.CodeCompileUnit>) 和类 (<xref:System.CodeDom.CodeTypeDeclaration>)，指定生成的源文件的名称并声明 `Main` 方法。</span><span class="sxs-lookup"><span data-stu-id="34e45-114">Define the global fields that are to be used in the class to reference the assembly (<xref:System.CodeDom.CodeCompileUnit>) and class (<xref:System.CodeDom.CodeTypeDeclaration>), specify the name of the generated source file, and declare the `Main` method.</span></span>  
  
     <span data-ttu-id="34e45-115">[!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]  [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="34e45-115">[!code-csharp[CodeDOM Class Sample Main#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample Main/CS/program.cs#1)]  [!code-vb[CodeDOM Class Sample Main#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample Main/VB/program.vb#1)]</span></span>  
  
### <a name="to-initialize-the-codedom-graph"></a><span data-ttu-id="34e45-116">初始化 CodeDOM 图</span><span class="sxs-lookup"><span data-stu-id="34e45-116">To initialize the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="34e45-117">在控制台应用程序类的构造函数中，初始化程序集和类，并向 CodeDOM 图添加适当的声明。</span><span class="sxs-lookup"><span data-stu-id="34e45-117">In the constructor for the console application class, initialize the assembly and class, and add the appropriate declarations to the CodeDOM graph.</span></span>  
  
     <span data-ttu-id="34e45-118">[!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]  [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]</span><span class="sxs-lookup"><span data-stu-id="34e45-118">[!code-csharp[CodeDOM Class Sample#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#2)]  [!code-vb[CodeDOM Class Sample#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#2)]</span></span>  
  
### <a name="to-add-members-to-the-codedom-graph"></a><span data-ttu-id="34e45-119">向 CodeDOM 图添加成员</span><span class="sxs-lookup"><span data-stu-id="34e45-119">To add members to the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="34e45-120">通过向类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性添加 <xref:System.CodeDom.CodeMemberField> 对象，向 CodeDOM 图添加字段。</span><span class="sxs-lookup"><span data-stu-id="34e45-120">Add fields to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberField> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="34e45-121">[!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]  [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]</span><span class="sxs-lookup"><span data-stu-id="34e45-121">[!code-csharp[CodeDOM Class Sample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#3)]  [!code-vb[CodeDOM Class Sample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#3)]</span></span>  
  
-   <span data-ttu-id="34e45-122">通过向类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性添加 <xref:System.CodeDom.CodeMemberProperty> 对象，向 CodeDOM 图添加属性。</span><span class="sxs-lookup"><span data-stu-id="34e45-122">Add properties to the CodeDOM graph by adding <xref:System.CodeDom.CodeMemberProperty> objects to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="34e45-123">[!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]  [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]</span><span class="sxs-lookup"><span data-stu-id="34e45-123">[!code-csharp[CodeDOM Class Sample#4](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#4)]  [!code-vb[CodeDOM Class Sample#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#4)]</span></span>  
  
-   <span data-ttu-id="34e45-124">通过向类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性添加 <xref:System.CodeDom.CodeMemberMethod> 对象，向 CodeDOM 图添加方法。</span><span class="sxs-lookup"><span data-stu-id="34e45-124">Add a method to the CodeDOM graph by adding a <xref:System.CodeDom.CodeMemberMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="34e45-125">[!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]  [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]</span><span class="sxs-lookup"><span data-stu-id="34e45-125">[!code-csharp[CodeDOM Class Sample#5](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#5)]  [!code-vb[CodeDOM Class Sample#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#5)]</span></span>  
  
-   <span data-ttu-id="34e45-126">通过向类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性添加 <xref:System.CodeDom.CodeConstructor> 对象，向 CodeDOM 图添加构造函数。</span><span class="sxs-lookup"><span data-stu-id="34e45-126">Add a constructor to the CodeDOM graph by adding a <xref:System.CodeDom.CodeConstructor> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="34e45-127">[!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]  [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]</span><span class="sxs-lookup"><span data-stu-id="34e45-127">[!code-csharp[CodeDOM Class Sample#6](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#6)]  [!code-vb[CodeDOM Class Sample#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#6)]</span></span>  
  
-   <span data-ttu-id="34e45-128">通过向类的 <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> 属性添加 <xref:System.CodeDom.CodeEntryPointMethod> 对象，向 CodeDOM 图添加入口点。</span><span class="sxs-lookup"><span data-stu-id="34e45-128">Add an entry point to the CodeDOM graph by adding a <xref:System.CodeDom.CodeEntryPointMethod> object to the <xref:System.CodeDom.CodeTypeDeclaration.Members%2A> property of the class.</span></span>  
  
     <span data-ttu-id="34e45-129">[!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]  [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]</span><span class="sxs-lookup"><span data-stu-id="34e45-129">[!code-csharp[CodeDOM Class Sample#7](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#7)]  [!code-vb[CodeDOM Class Sample#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#7)]</span></span>  
  
### <a name="to-generate-the-code-from-the-codedom-graph"></a><span data-ttu-id="34e45-130">从 CodeDOM 图生成代码</span><span class="sxs-lookup"><span data-stu-id="34e45-130">To generate the code from the CodeDOM graph</span></span>  
  
-   <span data-ttu-id="34e45-131">通过调用 <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> 方法，从 CodeDOM 图生成源代码。</span><span class="sxs-lookup"><span data-stu-id="34e45-131">Generate source code from the CodeDOM graph by calling the <xref:System.CodeDom.Compiler.CodeDomProvider.GenerateCodeFromCompileUnit%2A> method.</span></span>  
  
     <span data-ttu-id="34e45-132">[!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]  [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]</span><span class="sxs-lookup"><span data-stu-id="34e45-132">[!code-csharp[CodeDOM Class Sample#8](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#8)]  [!code-vb[CodeDOM Class Sample#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#8)]</span></span>  
  
### <a name="to-create-the-graph-and-generate-the-code"></a><span data-ttu-id="34e45-133">创建图并生成代码</span><span class="sxs-lookup"><span data-stu-id="34e45-133">To create the graph and generate the code</span></span>  
  
1.  <span data-ttu-id="34e45-134">将以上步骤中创建的方法添加到第一步中定义的 `Main` 方法中。</span><span class="sxs-lookup"><span data-stu-id="34e45-134">Add the methods created in the preceding steps to the `Main` method defined in the first step.</span></span>  
  
     <span data-ttu-id="34e45-135">[!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]  [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]</span><span class="sxs-lookup"><span data-stu-id="34e45-135">[!code-csharp[CodeDOM Class Sample#9](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#9)]  [!code-vb[CodeDOM Class Sample#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#9)]</span></span>  
  
2.  <span data-ttu-id="34e45-136">编译并执行生成类。</span><span class="sxs-lookup"><span data-stu-id="34e45-136">Compile and execute the generating class.</span></span>  
  
## <a name="example"></a><span data-ttu-id="34e45-137">示例</span><span class="sxs-lookup"><span data-stu-id="34e45-137">Example</span></span>  
 <span data-ttu-id="34e45-138">以下代码示例显示了上述步骤中的代码。</span><span class="sxs-lookup"><span data-stu-id="34e45-138">The following code example shows the code from the preceding steps.</span></span>  
  
 <span data-ttu-id="34e45-139">[!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)] [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]</span><span class="sxs-lookup"><span data-stu-id="34e45-139">[!code-csharp[CodeDOM Class Sample#1](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/program.cs#1)] [!code-vb[CodeDOM Class Sample#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/program.vb#1)]</span></span>  
  
 <span data-ttu-id="34e45-140">编译和执行以上示例后，会生成以下源代码。</span><span class="sxs-lookup"><span data-stu-id="34e45-140">When the preceding example is compiled and executed, it produces the following source code.</span></span>  
  
 <span data-ttu-id="34e45-141">[!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)] [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]</span><span class="sxs-lookup"><span data-stu-id="34e45-141">[!code-csharp[CodeDOM Class Sample#99](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeDOM Class Sample/CS/SampleCode.cs#99)] [!code-vb[CodeDOM Class Sample#99](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeDOM Class Sample/VB/SampleCode.vb#99)]</span></span>  
  
 <span data-ttu-id="34e45-142">生成的源代码经过编译和执行后会产生以下输出。</span><span class="sxs-lookup"><span data-stu-id="34e45-142">The generated source code produces the following output when compiled and executed.</span></span>  
  
```  
The object:  
 width = 5.3,  
 height = 6.9,  
 area = 36.57  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="34e45-143">编译代码</span><span class="sxs-lookup"><span data-stu-id="34e45-143">Compiling the Code</span></span>  
  
-   <span data-ttu-id="34e45-144">需要 `FullTrust` 权限集才可成功执行此代码示例。</span><span class="sxs-lookup"><span data-stu-id="34e45-144">This code example requires the `FullTrust` permission set to execute successfully.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34e45-145">另请参阅</span><span class="sxs-lookup"><span data-stu-id="34e45-145">See Also</span></span>  
 <span data-ttu-id="34e45-146">[使用 CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md) </span><span class="sxs-lookup"><span data-stu-id="34e45-146">[Using the CodeDOM](../../../docs/framework/reflection-and-codedom/using-the-codedom.md) </span></span>  
 [<span data-ttu-id="34e45-147">从 CodeDOM 图生成和编译源代码</span><span class="sxs-lookup"><span data-stu-id="34e45-147">Generating and Compiling Source Code from a CodeDOM Graph</span></span>](../../../docs/framework/reflection-and-codedom/generating-and-compiling-source-code-from-a-codedom-graph.md)

