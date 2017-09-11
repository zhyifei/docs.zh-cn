---
title: "在 Visual Basic 中操作文件和目录"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- files, reading text
- reading files, text
- I/O [Visual Basic], walkthroughs
- text, writing to files
- text, reading from files
- reading text from files, walkthroughs
- Visual Basic code, file access
- files, writing text
- I/O [Visual Basic], writing text to files
- file access, walkthroughs
- writing to files, walkthroughs
- I/O [Visual Basic], reading text from files
ms.assetid: cae77565-9f78-4e46-8e42-eb2f9f8e1ffd
caps.latest.revision: 49
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 9e66d062df07fc23dfbd5d509e08ccd08813db15
ms.contentlocale: zh-cn
ms.lasthandoff: 07/28/2017

---
# <a name="walkthrough-manipulating-files-and-directories-in-visual-basic"></a><span data-ttu-id="cf4e9-102">演练：在 Visual Basic 中操作文件和目录</span><span class="sxs-lookup"><span data-stu-id="cf4e9-102">Walkthrough: Manipulating Files and Directories in Visual Basic</span></span>
<span data-ttu-id="cf4e9-103">本演练简单介绍 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 中文件 I/O 的基础知识。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-103">This walkthrough provides an introduction to the fundamentals of file I/O in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="cf4e9-104">描述如何创建列出并检查目录中文本文件的小型应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-104">It describes how to create a small application that lists and examines text files in a directory.</span></span> <span data-ttu-id="cf4e9-105">对于所选的每个文本文件，该应用程序都会提供文件属性和内容的第一行。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-105">For each selected text file, the application provides file attributes and the first line of content.</span></span> <span data-ttu-id="cf4e9-106">可以选择将信息写入日志文件中。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-106">There is an option to write information to a log file.</span></span>  
  
 <span data-ttu-id="cf4e9-107">本演练使用 `My.Computer.FileSystem Object` 的成员，这些成员可从 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] 中获得。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-107">This walkthrough uses members of the `My.Computer.FileSystem Object`, which are available in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)].</span></span> <span data-ttu-id="cf4e9-108">有关更多信息，请参见<xref:Microsoft.VisualBasic.FileIO.FileSystem>。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-108">See <xref:Microsoft.VisualBasic.FileIO.FileSystem> for more information.</span></span> <span data-ttu-id="cf4e9-109">本演练结尾部分提供等效示例，该示例使用来自 <xref:System.IO> 命名空间的类。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-109">At the end of the walkthrough, an equivalent example is provided that uses classes from the <xref:System.IO> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-the-project"></a><span data-ttu-id="cf4e9-110">创建项目</span><span class="sxs-lookup"><span data-stu-id="cf4e9-110">To create the project</span></span>  
  
1.  <span data-ttu-id="cf4e9-111">在“文件”菜单上，单击“新建项目”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-111">On the **File** menu, click **New Project**.</span></span>  
  
     <span data-ttu-id="cf4e9-112">此时将出现 “新建项目” 对话框。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-112">The **New Project** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="cf4e9-113">在“已安装的模板”窗格中，展开“Visual Basic”，然后单击“Windows”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-113">In the **Installed Templates** pane, expand **Visual Basic**, and then click **Windows**.</span></span> <span data-ttu-id="cf4e9-114">在中间的“模板”窗格中，单击“Windows 窗体应用程序”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-114">In the **Templates** pane in the middle, click **Windows Forms Application**.</span></span>  
  
3.  <span data-ttu-id="cf4e9-115">在“名称”框中，键入 `FileExplorer` 以设置项目名称，然后单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-115">In the **Name** box, type `FileExplorer` to set the project name, and then click **OK**.</span></span>  
  
     [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)]<span data-ttu-id="cf4e9-116"> 会将项目添加到“解决方案资源管理器”中，并打开 Windows 窗体设计器。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-116"> adds the project to **Solution Explorer**, and the Windows Forms Designer opens.</span></span>  
  
4.  <span data-ttu-id="cf4e9-117">将下表中的控件添加到窗体，并设置控件属性相应的值。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-117">Add the controls in the following table to the form, and set the corresponding values for their properties.</span></span>  
  
    |<span data-ttu-id="cf4e9-118">控件</span><span class="sxs-lookup"><span data-stu-id="cf4e9-118">Control</span></span>|<span data-ttu-id="cf4e9-119">属性</span><span class="sxs-lookup"><span data-stu-id="cf4e9-119">Property</span></span>|<span data-ttu-id="cf4e9-120">值</span><span class="sxs-lookup"><span data-stu-id="cf4e9-120">Value</span></span>|  
    |-------------|--------------|-----------|  
    |<span data-ttu-id="cf4e9-121">**ListBox**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-121">**ListBox**</span></span>|<span data-ttu-id="cf4e9-122">**Name**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-122">**Name**</span></span>|`filesListBox`|  
    |<span data-ttu-id="cf4e9-123">**Button**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-123">**Button**</span></span>|<span data-ttu-id="cf4e9-124">**Name**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-124">**Name**</span></span><br /><br /> <span data-ttu-id="cf4e9-125">**文本**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-125">**Text**</span></span>|`browseButton`<br /><br /> <span data-ttu-id="cf4e9-126">**浏览**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-126">**Browse**</span></span>|  
    |<span data-ttu-id="cf4e9-127">**Button**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-127">**Button**</span></span>|<span data-ttu-id="cf4e9-128">**Name**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-128">**Name**</span></span><br /><br /> <span data-ttu-id="cf4e9-129">**文本**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-129">**Text**</span></span>|`examineButton`<br /><br /> <span data-ttu-id="cf4e9-130">**检查**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-130">**Examine**</span></span>|  
    |<span data-ttu-id="cf4e9-131">**CheckBox**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-131">**CheckBox**</span></span>|<span data-ttu-id="cf4e9-132">**Name**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-132">**Name**</span></span><br /><br /> <span data-ttu-id="cf4e9-133">**文本**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-133">**Text**</span></span>|`saveCheckBox`<br /><br /> <span data-ttu-id="cf4e9-134">**保存结果**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-134">**Save Results**</span></span>|  
    |<span data-ttu-id="cf4e9-135">**FolderBrowserDialog**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-135">**FolderBrowserDialog**</span></span>|<span data-ttu-id="cf4e9-136">**Name**</span><span class="sxs-lookup"><span data-stu-id="cf4e9-136">**Name**</span></span>|`FolderBrowserDialog1`|  
  
### <a name="to-select-a-folder-and-list-files-in-a-folder"></a><span data-ttu-id="cf4e9-137">选择一个文件夹，并列出文件夹中的文件</span><span class="sxs-lookup"><span data-stu-id="cf4e9-137">To select a folder, and list files in a folder</span></span>  
  
1.  <span data-ttu-id="cf4e9-138">通过双击窗体上的控件，创建 `browseButton` 的 `Click` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-138">Create a `Click` event handler for `browseButton` by double-clicking the control on the form.</span></span> <span data-ttu-id="cf4e9-139">代码编辑器随即打开。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-139">The Code Editor opens.</span></span>  
  
2.  <span data-ttu-id="cf4e9-140">将以下代码添加到 `Click` 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-140">Add the following code to the `Click` event handler.</span></span>  
  
     <span data-ttu-id="cf4e9-141">[!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-141">[!code-vb[VbVbcnMyFileSystem#103](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_1.vb)]</span></span>  
  
     <span data-ttu-id="cf4e9-142">`FolderBrowserDialog1.ShowDialog` 调用将打开“浏览文件夹”对话框。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-142">The `FolderBrowserDialog1.ShowDialog` call opens the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="cf4e9-143">用户单击“确定”后，<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> 属性作为参数发送给在下一步中添加的 `ListFiles` 方法。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-143">After the user clicks **OK**, the <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property is sent as an argument to the `ListFiles` method, which is added in the next step.</span></span>  
  
3.  <span data-ttu-id="cf4e9-144">添加以下 `ListFiles` 方法。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-144">Add the following `ListFiles` method.</span></span>  
  
     <span data-ttu-id="cf4e9-145">[!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-145">[!code-vb[VbVbcnMyFileSystem#104](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_2.vb)]</span></span>  
  
     <span data-ttu-id="cf4e9-146">此代码首先会清除“ListBox”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-146">This code first clears the **ListBox**.</span></span>  
  
     <span data-ttu-id="cf4e9-147"><xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> 方法然后检索字符串集合，一个字符串对应目录中的一个文件。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-147">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFiles%2A> method then retrieves a collection of strings, one for each file in the directory.</span></span> <span data-ttu-id="cf4e9-148">`GetFiles` 方法接受一个搜索模式参数来检索与特定模式匹配的文件。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-148">The `GetFiles` method accepts a search pattern argument to retrieve files that match a particular pattern.</span></span> <span data-ttu-id="cf4e9-149">在此示例中，仅返回具有 .txt 扩展名的文件。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-149">In this example, only files that have the extension .txt are returned.</span></span>  
  
     <span data-ttu-id="cf4e9-150">通过 `GetFiles` 方法返回的字符串随后将添加到“ListBox”中。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-150">The strings that are returned by the `GetFiles` method are then added to the **ListBox**.</span></span>  
  
4.  <span data-ttu-id="cf4e9-151">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-151">Run the application.</span></span> <span data-ttu-id="cf4e9-152">单击“浏览”按钮。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-152">Click the **Browse** button.</span></span> <span data-ttu-id="cf4e9-153">在“浏览文件夹”对话框中，浏览到包含 .txt 文件的文件夹，然后选择该文件夹，并单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-153">In the **Browse For Folder** dialog box, browse to a folder that contains .txt files, and then select the folder and click **OK**.</span></span>  
  
     <span data-ttu-id="cf4e9-154">`ListBox` 包含所选文件夹中 .txt 文件的列表。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-154">The `ListBox` contains a list of .txt files in the selected folder.</span></span>  
  
5.  <span data-ttu-id="cf4e9-155">停止运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-155">Stop running the application.</span></span>  
  
### <a name="to-obtain-attributes-of-a-file-and-content-from-a-text-file"></a><span data-ttu-id="cf4e9-156">从文本文件获取文件的属性和内容</span><span class="sxs-lookup"><span data-stu-id="cf4e9-156">To obtain attributes of a file, and content from a text file</span></span>  
  
1.  <span data-ttu-id="cf4e9-157">通过双击窗体上的控件，创建 `examineButton` 的 `Click` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-157">Create a `Click` event handler for `examineButton` by double-clicking the control on the form.</span></span>  
  
2.  <span data-ttu-id="cf4e9-158">将以下代码添加到 `Click` 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-158">Add the following code to the `Click` event handler.</span></span>  
  
     <span data-ttu-id="cf4e9-159">[!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-159">[!code-vb[VbVbcnMyFileSystem#105](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_3.vb)]</span></span>  
  
     <span data-ttu-id="cf4e9-160">该代码验证是否在 `ListBox` 中选中某项。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-160">The code verifies that an item is selected in the `ListBox`.</span></span> <span data-ttu-id="cf4e9-161">然后，将从 `ListBox` 获取文件路径项。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-161">It then obtains the file path entry from the `ListBox`.</span></span> <span data-ttu-id="cf4e9-162"><xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> 方法用于检查文件是否仍然存在。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-162">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.FileExists%2A> method is used to check whether the file still exists.</span></span>  
  
     <span data-ttu-id="cf4e9-163">该文件路径作为参数发送给下一步中添加的 `GetTextForOutput` 方法。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-163">The file path is sent as an argument to the `GetTextForOutput` method, which is added in the next step.</span></span> <span data-ttu-id="cf4e9-164">此方法返回一个包含文件信息字符串。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-164">This method returns a string that contains file information.</span></span> <span data-ttu-id="cf4e9-165">该文件信息将出现在“MessageBox”中。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-165">The file information appears in a **MessageBox**.</span></span>  
  
3.  <span data-ttu-id="cf4e9-166">添加以下 `GetTextForOutput` 方法。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-166">Add the following `GetTextForOutput` method.</span></span>  
  
     <span data-ttu-id="cf4e9-167">[!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-167">[!code-vb[VbVbcnMyFileSystem#107](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_4.vb)]</span></span>  
  
     <span data-ttu-id="cf4e9-168">该代码使用 <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> 方法来获取文件参数。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-168">The code uses the <xref:Microsoft.VisualBasic.FileIO.FileSystem.GetFileInfo%2A> method to obtain file parameters.</span></span> <span data-ttu-id="cf4e9-169">文件参数添加到 <xref:System.Text.StringBuilder>。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-169">The file parameters are added to a <xref:System.Text.StringBuilder>.</span></span>  
  
     <span data-ttu-id="cf4e9-170"><xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> 方法将文件内容读取到 <xref:System.IO.StreamReader>。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-170">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.OpenTextFileReader%2A> method reads the file contents into a <xref:System.IO.StreamReader>.</span></span> <span data-ttu-id="cf4e9-171">该内容的第一行是从 `StreamReader` 获取的，然后将添加到 `StringBuilder`。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-171">The first line of the contents is obtained from the `StreamReader` and is added to the `StringBuilder`.</span></span>  
  
4.  <span data-ttu-id="cf4e9-172">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-172">Run the application.</span></span> <span data-ttu-id="cf4e9-173">单击“浏览”，然后浏览到包含 .txt 文件的文件夹。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-173">Click **Browse**, and browse to a folder that contains .txt files.</span></span> <span data-ttu-id="cf4e9-174">单击“确定”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-174">Click **OK**.</span></span>  
  
     <span data-ttu-id="cf4e9-175">在 `ListBox` 中选择一个文件，然后单击“检查”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-175">Select a file in the `ListBox`, and then click **Examine**.</span></span> <span data-ttu-id="cf4e9-176">`MessageBox` 显示文件信息。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-176">A `MessageBox` shows the file information.</span></span>  
  
5.  <span data-ttu-id="cf4e9-177">停止运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-177">Stop running the application.</span></span>  
  
### <a name="to-add-a-log-entry"></a><span data-ttu-id="cf4e9-178">添加日志项目</span><span class="sxs-lookup"><span data-stu-id="cf4e9-178">To add a log entry</span></span>  
  
1.  <span data-ttu-id="cf4e9-179">将以下代码添加到 `examineButton_Click` 事件处理程序末尾。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-179">Add the following code to the end of the `examineButton_Click` event handler.</span></span>  
  
     <span data-ttu-id="cf4e9-180">[!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-180">[!code-vb[VbVbcnMyFileSystem#106](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_5.vb)]</span></span>  
  
     <span data-ttu-id="cf4e9-181">该代码设置日志文件路径以便将日志文件放在与所选文件相同的目录中。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-181">The code sets the log file path to put the log file in the same directory as that of the selected file.</span></span> <span data-ttu-id="cf4e9-182">日志项目的文本设置为当前日期和文件信息后的时间。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-182">The text of the log entry is set to the current date and time followed by the file information.</span></span>  
  
     <span data-ttu-id="cf4e9-183"><xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> 方法，其 `append` 参数设置为 `True`，用于创建日志条目。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-183">The <xref:Microsoft.VisualBasic.FileIO.FileSystem.WriteAllText%2A> method, with the `append` argument set to `True`, is used to create the log entry.</span></span>  
  
2.  <span data-ttu-id="cf4e9-184">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-184">Run the application.</span></span> <span data-ttu-id="cf4e9-185">浏览到一个文本文件，在 `ListBox` 中选中它，选择“保存结果”复选框，然后再单击“检查”。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-185">Browse to a text file, select it in the `ListBox`, select the **Save Results** check box, and then click **Examine**.</span></span> <span data-ttu-id="cf4e9-186">验证日志条目是否写入 `log.txt` 文件。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-186">Verify that the log entry is written to the `log.txt` file.</span></span>  
  
3.  <span data-ttu-id="cf4e9-187">停止运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-187">Stop running the application.</span></span>  
  
### <a name="to-use-the-current-directory"></a><span data-ttu-id="cf4e9-188">使用当前目录</span><span class="sxs-lookup"><span data-stu-id="cf4e9-188">To use the current directory</span></span>  
  
1.  <span data-ttu-id="cf4e9-189">通过双击窗体，创建 `Form1_Load` 的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-189">Create an event handler for `Form1_Load` by double-clicking the form.</span></span>  
  
2.  <span data-ttu-id="cf4e9-190">将以下代码添加到该事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-190">Add the following code to the event handler.</span></span>  
  
     <span data-ttu-id="cf4e9-191">[!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-191">[!code-vb[VbVbcnMyFileSystem#102](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_6.vb)]</span></span>  
  
     <span data-ttu-id="cf4e9-192">此代码将文件夹浏览器的默认目录设置为当前目录。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-192">This code sets the default directory of the folder browser to the current directory.</span></span>  
  
3.  <span data-ttu-id="cf4e9-193">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-193">Run the application.</span></span> <span data-ttu-id="cf4e9-194">第一次单击“浏览”时，“浏览文件夹”对话框将打开到当前目录。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-194">When you click **Browse** the first time, the **Browse For Folder** dialog box opens to the current directory.</span></span>  
  
4.  <span data-ttu-id="cf4e9-195">停止运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-195">Stop running the application.</span></span>  
  
### <a name="to-selectively-enable-controls"></a><span data-ttu-id="cf4e9-196">有选择地启用控件</span><span class="sxs-lookup"><span data-stu-id="cf4e9-196">To selectively enable controls</span></span>  
  
1.  <span data-ttu-id="cf4e9-197">添加以下 `SetEnabled` 方法。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-197">Add the following `SetEnabled` method.</span></span>  
  
     <span data-ttu-id="cf4e9-198">[!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-198">[!code-vb[VbVbcnMyFileSystem#108](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_7.vb)]</span></span>  
  
     <span data-ttu-id="cf4e9-199">`SetEnabled` 方法启用还是禁用控件是由是否选中 `ListBox` 中的项决定的。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-199">The `SetEnabled` method enables or disables controls depending on whether an item is selected in the `ListBox`.</span></span>  
  
2.  <span data-ttu-id="cf4e9-200">通过双击窗体上的 `ListBox` 控件，创建 `filesListBox` 的 `SelectedIndexChanged` 事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-200">Create a `SelectedIndexChanged` event handler for `filesListBox` by double-clicking the `ListBox` control on the form.</span></span>  
  
3.  <span data-ttu-id="cf4e9-201">在新的 `filesListBox_SelectedIndexChanged` 事件处理程序中添加对 `SetEnabled` 的调用。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-201">Add a call to `SetEnabled` in the new `filesListBox_SelectedIndexChanged` event handler.</span></span>  
  
4.  <span data-ttu-id="cf4e9-202">在 `browseButton_Click` 事件处理程序末尾添加对 `SetEnabled` 的调用。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-202">Add a call to `SetEnabled` at the end of the `browseButton_Click` event handler.</span></span>  
  
5.  <span data-ttu-id="cf4e9-203">在 `Form1_Load` 事件处理程序末尾添加对 `SetEnabled` 的调用。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-203">Add a call to `SetEnabled` at the end of the `Form1_Load` event handler.</span></span>  
  
6.  <span data-ttu-id="cf4e9-204">运行该应用程序。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-204">Run the application.</span></span> <span data-ttu-id="cf4e9-205">如果在 `ListBox` 中未选中任何项，将禁用“保存结果”复选框和“检查”按钮。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-205">The **Save Results** check box and the **Examine** button are disabled if an item is not selected in the `ListBox`.</span></span>  
  
## <a name="full-example-using-mycomputerfilesystem"></a><span data-ttu-id="cf4e9-206">使用 My.Computer.FileSystem 的完整示例</span><span class="sxs-lookup"><span data-stu-id="cf4e9-206">Full example using My.Computer.FileSystem</span></span>  
 <span data-ttu-id="cf4e9-207">以下是完整示例。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-207">Following is the complete example.</span></span>  
  
 <span data-ttu-id="cf4e9-208">[!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-208">[!code-vb[VbVbcnMyFileSystem#101](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_8.vb)]</span></span>  
  
## <a name="full-example-using-systemio"></a><span data-ttu-id="cf4e9-209">使用 System.IO 的完整示例</span><span class="sxs-lookup"><span data-stu-id="cf4e9-209">Full example using System.IO</span></span>  
 <span data-ttu-id="cf4e9-210">以下等效示例使用来自 <xref:System.IO> 命名空间的类，而不使用 `My.Computer.FileSystem` 对象。</span><span class="sxs-lookup"><span data-stu-id="cf4e9-210">The following equivalent example uses classes from the <xref:System.IO> namespace instead of using `My.Computer.FileSystem` objects.</span></span>  
  
 <span data-ttu-id="cf4e9-211">[!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]</span><span class="sxs-lookup"><span data-stu-id="cf4e9-211">[!code-vb[VbVbcnMyFileSystem#111](../../../../visual-basic/developing-apps/programming/drives-directories-files/codesnippet/VisualBasic/walkthrough-manipulating-files-and-directories_9.vb)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf4e9-212">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf4e9-212">See Also</span></span>  
 <span data-ttu-id="cf4e9-213"><xref:System.IO></span><span class="sxs-lookup"><span data-stu-id="cf4e9-213"><xref:System.IO></span></span>   
 <span data-ttu-id="cf4e9-214"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span><span class="sxs-lookup"><span data-stu-id="cf4e9-214"><xref:Microsoft.VisualBasic.FileIO.FileSystem></span></span>   
 <span data-ttu-id="cf4e9-215"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A></span><span class="sxs-lookup"><span data-stu-id="cf4e9-215"><xref:Microsoft.VisualBasic.FileIO.FileSystem.CurrentDirectory%2A></span></span>   
 [<span data-ttu-id="cf4e9-216">演练：使用 .NET Framework 方法操作文件</span><span class="sxs-lookup"><span data-stu-id="cf4e9-216">Walkthrough: Manipulating Files by Using .NET Framework Methods</span></span>](../../../../visual-basic/developing-apps/programming/drives-directories-files/walkthrough-manipulating-files-by-using-net-framework-methods.md)

