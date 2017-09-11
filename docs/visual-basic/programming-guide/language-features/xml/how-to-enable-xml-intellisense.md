---
title: "如何︰ 启用 XML IntelliSense 在 Visual Basic |Microsoft 文档"
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
helpviewer_keywords:
- XML IntelliSense [Visual Basic]
- XML [Visual Basic], IntelliSense
- IntelliSense [Visual Basic], XML
ms.assetid: af67d0ee-a4a6-4abf-9c07-5a8cfe80d111
caps.latest.revision: 25
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: e367016c93586ad34492628b6a4384a5ef1b6acd
ms.contentlocale: zh-cn
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="99dec-102">如何：在 Visual Basic 中启用 XML IntelliSense</span><span class="sxs-lookup"><span data-stu-id="99dec-102">How to: Enable XML IntelliSense in Visual Basic</span></span>
<span data-ttu-id="99dec-103">在 Visual Basic 中的 XML IntelliSense 提供了完整单词的 XML 架构中定义的元素。</span><span class="sxs-lookup"><span data-stu-id="99dec-103">XML IntelliSense in Visual Basic provides word completion for elements that are defined in an XML schema.</span></span> <span data-ttu-id="99dec-104">若要启用 XML IntelliSense 在 Visual Basic 中，必须执行以下操作︰</span><span class="sxs-lookup"><span data-stu-id="99dec-104">To enable XML IntelliSense in Visual Basic, you must do the following:</span></span>  
  
1.  <span data-ttu-id="99dec-105">获取您的应用程序将读取或写入的 XML 文件的 XML 架构 (XSD) 文件。</span><span class="sxs-lookup"><span data-stu-id="99dec-105">Obtain the XML schema (XSD) file or files for the XML files that your application will read from or write to.</span></span>  
  
2.  <span data-ttu-id="99dec-106">在项目中包含的 XML 架构文件。</span><span class="sxs-lookup"><span data-stu-id="99dec-106">Include the XML schema files in your project.</span></span>  
  
3.  <span data-ttu-id="99dec-107">导入您的代码文件或项目的目标命名空间或命名空间。</span><span class="sxs-lookup"><span data-stu-id="99dec-107">Import the target namespace or namespaces into your code file or project.</span></span> <span data-ttu-id="99dec-108">由标识目标命名空间`targetNamespace`或`tns`XSD 架构的属性。</span><span class="sxs-lookup"><span data-stu-id="99dec-108">A target namespace is identified by the `targetNamespace` or `tns` attribute of your XSD schema.</span></span>  
  
     <span data-ttu-id="99dec-109">若要导入目标命名空间，请使用`Imports`语句，或通过将所有代码文件的命名空间添加到项目中**引用**项目设计器的页面。</span><span class="sxs-lookup"><span data-stu-id="99dec-109">To import a target namespace, use the `Imports` statement, or add a namespace for all code files in a project by using the **References** page of the Project Designer.</span></span>  
  
 <span data-ttu-id="99dec-110">功能在 Visual Basic 中的 XML IntelliSense 的详细信息，请参阅[Visual Basic 中的 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)。</span><span class="sxs-lookup"><span data-stu-id="99dec-110">For more information on the capabilities of XML IntelliSense in Visual Basic, see [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md).</span></span> <span data-ttu-id="99dec-111">导入 XML 命名空间的详细信息，请参阅[Imports 语句 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md)或[，项目设计器 (Visual Basic 中) 引用页](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic)。</span><span class="sxs-lookup"><span data-stu-id="99dec-111">For more information on importing XML namespaces, see [Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) or [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic).</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
 <span data-ttu-id="99dec-112">![视频链接](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo")本主题的视频版本，请参阅[视频帮助︰ 在 Visual Basic 中启用 XML IntelliSense](http://go.microsoft.com/fwlink/?LinkId=102466)。</span><span class="sxs-lookup"><span data-stu-id="99dec-112">![link to video](../../../../visual-basic/programming-guide/language-features/xml/media/playvideo.gif "PlayVideo") For a video version of this topic, see [Video How to: Enable XML IntelliSense in Visual Basic](http://go.microsoft.com/fwlink/?LinkId=102466).</span></span> <span data-ttu-id="99dec-113">有关相关的视频演示，请参阅[启用 XML IntelliSense 和使用 XML 命名空间如何实现？](http://go.microsoft.com/fwlink/?LinkId=143035)。</span><span class="sxs-lookup"><span data-stu-id="99dec-113">For a related video demonstration, see [How Do I Enable XML IntelliSense and Use XML Namespaces?](http://go.microsoft.com/fwlink/?LinkId=143035).</span></span>  
  
## <a name="enable-xml-intellisense-in-visual-basic"></a><span data-ttu-id="99dec-114">启用在 Visual Basic 中的 XML IntelliSense</span><span class="sxs-lookup"><span data-stu-id="99dec-114">Enable XML IntelliSense in Visual Basic</span></span>  
 <span data-ttu-id="99dec-115">如果您有一个 XML 文件，但您却没有为其 XSD 架构文件，在 SP1 中您可以创建 XSD 架构文件使用 XML 到架构向导。</span><span class="sxs-lookup"><span data-stu-id="99dec-115">If you have an XML file but you do not have an XSD schema file for it, in SP1 you can create an XSD schema file by using the XML to Schema Wizard.</span></span> <span data-ttu-id="99dec-116">您还可以使用架构推断 Visual Studio XML 编辑器中。</span><span class="sxs-lookup"><span data-stu-id="99dec-116">You can also use schema inference in the Visual Studio XML Editor.</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-the-xml-to-schema-wizard-requires-sp1"></a><span data-ttu-id="99dec-117">若要使用 XML 到架构向导创建一个 XML 文件的 XSD 架构文件 （需要 SP1）</span><span class="sxs-lookup"><span data-stu-id="99dec-117">To create an XSD schema file for an XML file by using the XML to Schema Wizard (requires SP1)</span></span>  
  
1.  <span data-ttu-id="99dec-118">在项目中，单击**添加新项**上**项目**菜单。</span><span class="sxs-lookup"><span data-stu-id="99dec-118">In your project, click **Add New Item** on the **Project** menu.</span></span>  
  
2.  <span data-ttu-id="99dec-119">选择**Xml 到架构**从项模板**数据**或**常用项**模板类别。</span><span class="sxs-lookup"><span data-stu-id="99dec-119">Select the **Xml to Schema** item template from either the **Data** or **Common Items** template categories.</span></span>  
  
3.  <span data-ttu-id="99dec-120">为提供一个文件名称或多个 XSD 文件，推断的架构集将存储在中，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="99dec-120">Provide a file name for the XSD file or files that the inferred schema set will be stored in, and then click **Add**.</span></span>  
  
4.  <span data-ttu-id="99dec-121">在**从 XML 文档推断 XML 架构集**窗口中，添加一个或多个要从中推断 XML 架构集的 XML 文档。</span><span class="sxs-lookup"><span data-stu-id="99dec-121">In the **Infer XML Schema set from XML documents** window, add one or more XML documents to infer the XML schema set from.</span></span>  
  
    -   <span data-ttu-id="99dec-122">若要添加包含 XML 文档使用文件资源管理器的文本文件，请单击**从文件添加**。</span><span class="sxs-lookup"><span data-stu-id="99dec-122">To add text files that contain XML documents by using File Explorer, click **Add from File**.</span></span>  
  
    -   <span data-ttu-id="99dec-123">若要添加从一个 HTTP 地址的 XML 文档，请单击**从 Web 添加**。</span><span class="sxs-lookup"><span data-stu-id="99dec-123">To add an XML document from an HTTP address, click **Add from Web**.</span></span>  
  
    -   <span data-ttu-id="99dec-124">若要复制或键入到向导的 XML 文档的内容，请单击**键入或粘贴 XML**。</span><span class="sxs-lookup"><span data-stu-id="99dec-124">To copy or type the contents of an XML document into the wizard, click **Type or paste XML**.</span></span>  
  
5.  <span data-ttu-id="99dec-125">指定你想要推断 XML 架构集，请单击的所有 XML 文档源时**确定**推断 XML 架构设置。</span><span class="sxs-lookup"><span data-stu-id="99dec-125">When you have specified all the XML document sources from which you want to infer the XML schema set, click **OK** to infer the XML schema set.</span></span> <span data-ttu-id="99dec-126">架构集将保存在项目文件夹下面的一个或多个 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="99dec-126">The schema set is saved in your project folder in one or more XSD files.</span></span> <span data-ttu-id="99dec-127">（每个 XML 命名空间的架构中，创建文件。）</span><span class="sxs-lookup"><span data-stu-id="99dec-127">(For each XML namespace in the schema, a file is created.)</span></span>  
  
#### <a name="to-create-an-xsd-schema-file-for-an-xml-file-by-using-schema-inference-in-the-visual-studio-xml-editor"></a><span data-ttu-id="99dec-128">若要通过使用 Visual Studio XML 编辑器中的架构推断创建 XSD 架构文件的 XML 文件</span><span class="sxs-lookup"><span data-stu-id="99dec-128">To create an XSD schema file for an XML file by using schema inference in the Visual Studio XML Editor</span></span>  
  
1.  <span data-ttu-id="99dec-129">编辑 Visual Studio XML 设计器中的 XML 文件。</span><span class="sxs-lookup"><span data-stu-id="99dec-129">Edit the XML file in the Visual Studio XML Designer.</span></span>  
  
2.  <span data-ttu-id="99dec-130">当光标位于某个位置在 XML 文件中， **XML**菜单显示。</span><span class="sxs-lookup"><span data-stu-id="99dec-130">When the cursor is somewhere in the XML file, the **XML** menu appears.</span></span> <span data-ttu-id="99dec-131">单击**Create Schema**上**XML**菜单。</span><span class="sxs-lookup"><span data-stu-id="99dec-131">Click **Create Schema** on the **XML** menu.</span></span> <span data-ttu-id="99dec-132">从从 XML 文件推断 XSD 架构创建 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="99dec-132">An XSD file is created from XSD schema inferred from the XML file.</span></span>  
  
3.  <span data-ttu-id="99dec-133">保存该 XSD 架构文件。</span><span class="sxs-lookup"><span data-stu-id="99dec-133">Save the XSD schema file.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="99dec-134">可以从多个用于具有相同的架构的 XML 文档推断出不同的 XSD 架构。</span><span class="sxs-lookup"><span data-stu-id="99dec-134">Different XSD schemas might be inferred from multiple XML documents that are intended to have the same schema.</span></span> <span data-ttu-id="99dec-135">这可发生在一个 XML 文件中而不是在另一台，找到特定的元素和属性时也顺序不同，例如包含元素。</span><span class="sxs-lookup"><span data-stu-id="99dec-135">This can occur when particular elements and attributes are found in one XML file and not in another, or when elements are included in different order, for example.</span></span> <span data-ttu-id="99dec-136">使用 XSD 架构推断时，应检查推断出的 XSD 架构的完整性和精确性。</span><span class="sxs-lookup"><span data-stu-id="99dec-136">You should review inferred XSD schemas for completeness and accuracy when you use XSD schema inference.</span></span>  
  
#### <a name="to-include-an-xsd-schema-file"></a><span data-ttu-id="99dec-137">若要包括的 XSD 架构文件</span><span class="sxs-lookup"><span data-stu-id="99dec-137">To include an XSD schema file</span></span>  
  
-   <span data-ttu-id="99dec-138">默认情况下，您无法看到在 Visual Basic 项目的 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="99dec-138">By default, you cannot see XSD files in Visual Basic projects.</span></span> <span data-ttu-id="99dec-139">如果在您的项目的文件夹中已经包含 XSD 文件，请单击**显示所有文件**按钮**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="99dec-139">If your XSD file is already included in the folders for your project, click the **Show All Files** button in **Solution Explorer**.</span></span> <span data-ttu-id="99dec-140">找到 XSD 文件在**解决方案资源管理器**，用鼠标右键单击该文件，然后单击**将文件包括在项目**。</span><span class="sxs-lookup"><span data-stu-id="99dec-140">Locate the XSD file in **Solution Explorer**, right-click the file, and click **Include File in Project**.</span></span>  
  
-   <span data-ttu-id="99dec-141">如果 XSD 文件正在不属于您的项目，**解决方案资源管理器**，右键单击您要在其中存储 XSD 文件，指向的文件夹**添加**，然后单击**现有项**。</span><span class="sxs-lookup"><span data-stu-id="99dec-141">If your XSD file is not already part of your project, in **Solution Explorer**, right-click the folder in which you want to store the XSD file, point to **Add**, and then click **Existing Item**.</span></span> <span data-ttu-id="99dec-142">找到 XSD 文件，然后单击**添加**。</span><span class="sxs-lookup"><span data-stu-id="99dec-142">Locate your XSD file and then click **Add**.</span></span>  
  
#### <a name="to-import-an-xml-namespace-in-a-code-file"></a><span data-ttu-id="99dec-143">若要导入到代码文件中的 XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="99dec-143">To import an XML namespace in a code file</span></span>  
  
1.  <span data-ttu-id="99dec-144">标识从 XSD 架构的目标命名空间。</span><span class="sxs-lookup"><span data-stu-id="99dec-144">Identify the target namespace from your XSD schema.</span></span>  
  
2.  <span data-ttu-id="99dec-145">在代码文件的开头，添加`Imports`目标 XML 命名空间，如下面的示例中所示的语句。</span><span class="sxs-lookup"><span data-stu-id="99dec-145">At the beginning of the code file, add an `Imports` statement for the target XML namespace, as shown in the following example.</span></span>  
  
     <span data-ttu-id="99dec-146">[!code-vb[VbXMLSamples #&1;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="99dec-146">[!code-vb[VbXMLSamples#1](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_1.vb)]</span></span>  
  
     <span data-ttu-id="99dec-147">若要导入 XML 命名空间为默认命名空间，即应用于 XML 元素和属性不具有命名空间前缀的命名空间添加`Imports`目标默认 XML 命名空间的语句。</span><span class="sxs-lookup"><span data-stu-id="99dec-147">To import an XML namespace as the default namespace, that is, the namespace that is applied to XML elements and attributes that do not have a namespace prefix, add an `Imports` statement for the target default XML namespace.</span></span> <span data-ttu-id="99dec-148">不要指定命名空间前缀。</span><span class="sxs-lookup"><span data-stu-id="99dec-148">Do not specify a namespace prefix.</span></span> <span data-ttu-id="99dec-149">以下是一种`Imports`语句。</span><span class="sxs-lookup"><span data-stu-id="99dec-149">Following is an example of an `Imports` statement.</span></span>  
  
     <span data-ttu-id="99dec-150">[!code-vb[VbXmlSamples #&50;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="99dec-150">[!code-vb[VbXmlSamples#50](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/how-to-enable-xml-intellisense_2.vb)]</span></span>  
  
#### <a name="to-import-an-xml-namespace-for-all-files-in-a-project"></a><span data-ttu-id="99dec-151">若要导入项目中的所有文件的 XML 命名空间</span><span class="sxs-lookup"><span data-stu-id="99dec-151">To import an XML namespace for all files in a project</span></span>  
  
1.  <span data-ttu-id="99dec-152">在代码文件中导入的 XML 命名空间适用于该代码文件。</span><span class="sxs-lookup"><span data-stu-id="99dec-152">An XML namespace imported in a code file applies to that code file only.</span></span> <span data-ttu-id="99dec-153">若要导入适用于在项目中的所有代码文件的 XML 命名空间，请打开项目设计器，通过双击**我的项目**中**解决方案资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="99dec-153">To import an XML namespace that applies to all code files in a project, open the Project Designer by double-clicking **My Project** in **Solution Explorer**.</span></span>  
  
2.  <span data-ttu-id="99dec-154">在**引用**选项卡上，在**导入的命名空间**框中，键入完整的 XML 命名空间声明的形式目标 XML 命名空间 (例如， `<xmlns: ns="http://sampleNamespace">`)。</span><span class="sxs-lookup"><span data-stu-id="99dec-154">On the **References** tab, in the **Imported namespaces** box, type the target XML namespace in the form of a full XML namespace declaration (for example, `<xmlns: ns="http://sampleNamespace">`).</span></span> <span data-ttu-id="99dec-155">如果目标 XML 命名空间没有指定命名空间前缀，命名空间将为该项目的默认 XML 命名空间。</span><span class="sxs-lookup"><span data-stu-id="99dec-155">If the target XML namespace does not specify a namespace prefix, the namespace will be the default XML namespace for the project.</span></span>  
  
3.  <span data-ttu-id="99dec-156">单击**添加用户导入**。</span><span class="sxs-lookup"><span data-stu-id="99dec-156">Click **Add User Import**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="99dec-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="99dec-157">See Also</span></span>  
 <span data-ttu-id="99dec-158">[Imports 语句 (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span><span class="sxs-lookup"><span data-stu-id="99dec-158">[Imports Statement (XML Namespace)](../../../../visual-basic/language-reference/statements/imports-statement-xml-namespace.md) </span></span>  
<span data-ttu-id="99dec-159"> [项目设计器 ->“引用”页 (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span><span class="sxs-lookup"><span data-stu-id="99dec-159"> [References Page, Project Designer (Visual Basic)](https://docs.microsoft.com/visualstudio/ide/reference/references-page-project-designer-visual-basic) </span></span>  
<span data-ttu-id="99dec-160"> [在 Visual Basic 中的 XML IntelliSense](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span><span class="sxs-lookup"><span data-stu-id="99dec-160"> [XML IntelliSense in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/xml-intellisense.md)</span></span>

