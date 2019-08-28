---
title: 如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- directories [Windows Forms], choosing
- FolderBrowserDialog component [Windows Forms], choosing directories
- folders [Windows Forms], selecting
- folders [Windows Forms], choosing
- directories [Windows Forms], selecting
ms.assetid: 4593670e-7c7d-4661-b46b-4ffb63258adb
ms.openlocfilehash: fc19ea466f535f783d3b0537a973ce41c223902d
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046135"
---
# <a name="how-to-choose-folders-with-the-windows-forms-folderbrowserdialog-component"></a><span data-ttu-id="a43ff-102">如何：使用 Windows 窗体 FolderBrowserDialog 组件选择文件夹</span><span class="sxs-lookup"><span data-stu-id="a43ff-102">How to: Choose Folders with the Windows Forms FolderBrowserDialog Component</span></span>

<span data-ttu-id="a43ff-103">通常，在创建的 Windows 应用程序内，需要提示用户选择文件夹，最常用于保存一组文件。</span><span class="sxs-lookup"><span data-stu-id="a43ff-103">Often, within Windows applications you create, you will have to prompt users to select a folder, most frequently to save a set of files.</span></span> <span data-ttu-id="a43ff-104">Windows 窗体<xref:System.Windows.Forms.FolderBrowserDialog>组件允许你轻松完成此任务。</span><span class="sxs-lookup"><span data-stu-id="a43ff-104">The Windows Forms <xref:System.Windows.Forms.FolderBrowserDialog> component allows you to easily accomplish this task.</span></span>

### <a name="to-choose-folders-with-the-folderbrowserdialog-component"></a><span data-ttu-id="a43ff-105">使用 FolderBrowserDialog 组件选择文件夹</span><span class="sxs-lookup"><span data-stu-id="a43ff-105">To choose folders with the FolderBrowserDialog component</span></span>

1. <span data-ttu-id="a43ff-106">在过程<xref:System.Windows.Forms.FolderBrowserDialog>中, 检查组件的<xref:System.Windows.Forms.Form.DialogResult%2A>属性以查看对话框的关闭方式, 并<xref:System.Windows.Forms.FolderBrowserDialog>获取组件的<xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A>属性的值。</span><span class="sxs-lookup"><span data-stu-id="a43ff-106">In a procedure, check the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.Form.DialogResult%2A> property to see how the dialog box was closed and get the value of the <xref:System.Windows.Forms.FolderBrowserDialog> component's <xref:System.Windows.Forms.FolderBrowserDialog.SelectedPath%2A> property.</span></span>

2. <span data-ttu-id="a43ff-107">如果需要设置将在对话框的树视图中显示的最顶层文件夹, 请设置<xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A>属性, 该属性采用<xref:System.Environment.SpecialFolder>枚举的成员。</span><span class="sxs-lookup"><span data-stu-id="a43ff-107">If you need to set the top-most folder that will appear within the tree view of the dialog box, set the <xref:System.Windows.Forms.FolderBrowserDialog.RootFolder%2A> property, which takes a member of the <xref:System.Environment.SpecialFolder> enumeration.</span></span>

3. <span data-ttu-id="a43ff-108">此外, 您还可以设置<xref:System.Windows.Forms.FolderBrowserDialog.Description%2A>属性, 该属性指定在文件夹浏览器树视图顶部显示的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="a43ff-108">Additionally, you can set the <xref:System.Windows.Forms.FolderBrowserDialog.Description%2A> property, which specifies the text string that appears at the top of the folder-browser tree view.</span></span>

    <span data-ttu-id="a43ff-109">在下面的示例中, <xref:System.Windows.Forms.FolderBrowserDialog>组件用于选择文件夹, 类似于在 Visual Studio 中创建项目时, 系统会提示选择要保存的文件夹。</span><span class="sxs-lookup"><span data-stu-id="a43ff-109">In the example below, the <xref:System.Windows.Forms.FolderBrowserDialog> component is used to select a folder, similar to when you create a project in Visual Studio and are prompted to select a folder to save it in.</span></span> <span data-ttu-id="a43ff-110">在此示例中, 文件夹名称随后显示在窗体<xref:System.Windows.Forms.TextBox>上的控件中。</span><span class="sxs-lookup"><span data-stu-id="a43ff-110">In this example, the folder name is then displayed in a <xref:System.Windows.Forms.TextBox> control on the form.</span></span> <span data-ttu-id="a43ff-111">最好将该位置放置在可编辑的区域 (例如<xref:System.Windows.Forms.TextBox>控件) 中, 以便用户在出现错误或其他问题时可以编辑其选择。</span><span class="sxs-lookup"><span data-stu-id="a43ff-111">It is a good idea to place the location in an editable area, such as a <xref:System.Windows.Forms.TextBox> control, so that users may edit their selection in case of error or other issues.</span></span> <span data-ttu-id="a43ff-112">此示例假设窗体具有一个<xref:System.Windows.Forms.FolderBrowserDialog>组件和一个<xref:System.Windows.Forms.TextBox>控件。</span><span class="sxs-lookup"><span data-stu-id="a43ff-112">This example assumes a form with a <xref:System.Windows.Forms.FolderBrowserDialog> component and a <xref:System.Windows.Forms.TextBox> control.</span></span>

    ```vb
    Public Sub ChooseFolder()
        If FolderBrowserDialog1.ShowDialog() = DialogResult.OK Then
            TextBox1.Text = FolderBrowserDialog1.SelectedPath
        End If
    End Sub
    ```

    ```csharp
    public void ChooseFolder()
    {
        if (folderBrowserDialog1.ShowDialog() == DialogResult.OK)
        {
            textBox1.Text = folderBrowserDialog1.SelectedPath;
        }
    }
    ```

    ```cpp
    public:
       void ChooseFolder()
       {
          if (folderBrowserDialog1->ShowDialog() == DialogResult::OK)
          {
             textBox1->Text = folderBrowserDialog1->SelectedPath;
          }
       }
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="a43ff-113">若要使用此类, 程序集需要由<xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A>属性授予的权限级别, 该属性是<xref:System.Security.Permissions.FileIOPermissionAccess>枚举的一部分。</span><span class="sxs-lookup"><span data-stu-id="a43ff-113">To use this class, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.FileIOPermissionAttribute.PathDiscovery%2A> property, which is part of the <xref:System.Security.Permissions.FileIOPermissionAccess> enumeration.</span></span> <span data-ttu-id="a43ff-114">如果在部分信任上下文中运行，该进程可能会因特权不足而引发异常。</span><span class="sxs-lookup"><span data-stu-id="a43ff-114">If you are running in a partial-trust context, the process might throw an exception because of insufficient privileges.</span></span> <span data-ttu-id="a43ff-115">有关详细信息，请参阅[代码访问安全性基础知识](../../misc/code-access-security-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="a43ff-115">For more information, see [Code Access Security Basics](../../misc/code-access-security-basics.md).</span></span>

<span data-ttu-id="a43ff-116">有关如何保存文件的信息, 请参阅[如何:使用 SaveFileDialog 组件](how-to-save-files-using-the-savefiledialog-component.md)保存文件。</span><span class="sxs-lookup"><span data-stu-id="a43ff-116">For information on how to save files, see [How to: Save Files Using the SaveFileDialog Component](how-to-save-files-using-the-savefiledialog-component.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a43ff-117">请参阅</span><span class="sxs-lookup"><span data-stu-id="a43ff-117">See also</span></span>

- <xref:System.Windows.Forms.FolderBrowserDialog>
- [<span data-ttu-id="a43ff-118">FolderBrowserDialog 组件概述（Windows 窗体）</span><span class="sxs-lookup"><span data-stu-id="a43ff-118">FolderBrowserDialog Component Overview (Windows Forms)</span></span>](folderbrowserdialog-component-overview-windows-forms.md)
- [<span data-ttu-id="a43ff-119">FolderBrowserDialog 组件</span><span class="sxs-lookup"><span data-stu-id="a43ff-119">FolderBrowserDialog Component</span></span>](folderbrowserdialog-component-windows-forms.md)
