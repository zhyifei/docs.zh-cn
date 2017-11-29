---
title: "如何：提供文件操作进度对话框（C# 编程指南）"
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords: progress dialog [C#]
ms.assetid: 01b71fe7-8178-4dc8-aeb1-12053be7b51c
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0ac68b5aa6014db87b4f7a269ef73d0608371bd8
ms.sourcegitcommit: 7e99f66ef09d2903e22c789c67ff5a10aa953b2f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2017
---
# <a name="how-to-provide-a-progress-dialog-box-for-file-operations-c-programming-guide"></a><span data-ttu-id="03a99-102">如何：提供文件操作进度对话框（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="03a99-102">How to: Provide a Progress Dialog Box for File Operations (C# Programming Guide)</span></span>
<span data-ttu-id="03a99-103">如果在 <xref:Microsoft.VisualBasic?displayProperty=nameWithType> 命名空间中使用 <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> 方法，可以在 Windows 中提供显示文件操作进度的标准对话框。</span><span class="sxs-lookup"><span data-stu-id="03a99-103">You can provide a standard dialog box that shows progress on file operations in Windows if you use the <xref:Microsoft.VisualBasic.FileIO.FileSystem.CopyFile%28System.String%2CSystem.String%2CMicrosoft.VisualBasic.FileIO.UIOption%29> method in the <xref:Microsoft.VisualBasic?displayProperty=nameWithType> namespace.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-add-a-reference-in-visual-studio"></a><span data-ttu-id="03a99-104">在 Visual Studio 中添加引用</span><span class="sxs-lookup"><span data-stu-id="03a99-104">To add a reference in Visual Studio</span></span>  
  
1.  <span data-ttu-id="03a99-105">在菜单栏上，依次选择“项目”、“添加引用”。</span><span class="sxs-lookup"><span data-stu-id="03a99-105">On the menu bar, choose **Project**, **Add Reference**.</span></span>  
  
     <span data-ttu-id="03a99-106">此时将显示“引用管理器”对话框。</span><span class="sxs-lookup"><span data-stu-id="03a99-106">The **Reference Manager** dialog box appears.</span></span>  
  
2.  <span data-ttu-id="03a99-107">在“程序集”区域，选择“框架”（如果尚未选择它）。</span><span class="sxs-lookup"><span data-stu-id="03a99-107">In the **Assemblies** area, choose**Framework** if it isn’t already chosen.</span></span>  
  
3.  <span data-ttu-id="03a99-108">在名称列表中，选择“Microsoft.VisualBasic”复选框，然后再选择“确定”按钮以关闭对话框。</span><span class="sxs-lookup"><span data-stu-id="03a99-108">In the list of names, select the **Microsoft.VisualBasic** check box, and then choose the **OK** button to close the dialog box.</span></span>  
  
## <a name="example"></a><span data-ttu-id="03a99-109">示例</span><span class="sxs-lookup"><span data-stu-id="03a99-109">Example</span></span>  
 <span data-ttu-id="03a99-110">以下代码将 `sourcePath` 指定的目录复制到 `destinationPath` 指定的目录。</span><span class="sxs-lookup"><span data-stu-id="03a99-110">The following code copies the directory that `sourcePath` specifies into the directory that `destinationPath` specifies.</span></span> <span data-ttu-id="03a99-111">此代码还提供了标准的对话框，其中显示在操作完成前估计的剩余时间量。</span><span class="sxs-lookup"><span data-stu-id="03a99-111">This code also provides a standard dialog box that shows the estimated amount of time remaining before the operation finishes.</span></span>  
  
 [!code-csharp[csFilesandFolders#11](../../../csharp/programming-guide/file-system/codesnippet/CSharp/how-to-provide-a-progress-dialog-box-for-file-operations_1.cs)]  
  
## <a name="see-also"></a><span data-ttu-id="03a99-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03a99-112">See Also</span></span>  
 [<span data-ttu-id="03a99-113">文件系统和注册表（C# 编程指南）</span><span class="sxs-lookup"><span data-stu-id="03a99-113">File System and the Registry (C# Programming Guide)</span></span>](../../../csharp/programming-guide/file-system/index.md)
