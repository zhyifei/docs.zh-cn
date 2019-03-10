---
title: 如何：使用 Windows 窗体 RichTextBox 控件保存文件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- saving files
- RTF files [Windows Forms], saving in RichTextBox control
- examples [Windows Forms], text boxes
- saving files [Windows Forms], RichTextBox control
- files [Windows Forms], saving with RichTextBox control
- RichTextBox control [Windows Forms], saving files
- .rtf files [Windows Forms], saving in RichTextBox control
- text files [Windows Forms], saving from RichTextBox control
ms.assetid: 4a58ec19-84d1-4383-9110-298c06adcfca
ms.openlocfilehash: c9a5d471a58c646c786cf441ee7d7ec235788f10
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2019
ms.locfileid: "57723018"
---
# <a name="how-to-save-files-with-the-windows-forms-richtextbox-control"></a><span data-ttu-id="9f30d-102">如何：使用 Windows 窗体 RichTextBox 控件保存文件</span><span class="sxs-lookup"><span data-stu-id="9f30d-102">How to: Save Files with the Windows Forms RichTextBox Control</span></span>
<span data-ttu-id="9f30d-103">Windows 窗体<xref:System.Windows.Forms.RichTextBox>控件可以写入其显示在几种格式之一的信息：</span><span class="sxs-lookup"><span data-stu-id="9f30d-103">The Windows Forms <xref:System.Windows.Forms.RichTextBox> control can write the information it displays in one of several formats:</span></span>  
  
-   <span data-ttu-id="9f30d-104">纯文本</span><span class="sxs-lookup"><span data-stu-id="9f30d-104">Plain text</span></span>  
  
-   <span data-ttu-id="9f30d-105">Unicode 纯文本</span><span class="sxs-lookup"><span data-stu-id="9f30d-105">Unicode plain text</span></span>  
  
-   <span data-ttu-id="9f30d-106">丰富文本格式 (RTF)</span><span class="sxs-lookup"><span data-stu-id="9f30d-106">Rich-Text Format (RTF)</span></span>  
  
-   <span data-ttu-id="9f30d-107">用空格代替 OLE 对象的 RTF</span><span class="sxs-lookup"><span data-stu-id="9f30d-107">RTF with spaces in place of OLE objects</span></span>  
  
-   <span data-ttu-id="9f30d-108">使用 OLE 对象的文本表示形式的纯文本</span><span class="sxs-lookup"><span data-stu-id="9f30d-108">Plain text with a textual representation of OLE objects</span></span>  
  
 <span data-ttu-id="9f30d-109">若要保存文件，请调用<xref:System.Windows.Forms.RichTextBox.SaveFile%2A>方法。</span><span class="sxs-lookup"><span data-stu-id="9f30d-109">To save a file, call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method.</span></span> <span data-ttu-id="9f30d-110">此外可以使用**SaveFile**方法将数据保存到流。</span><span class="sxs-lookup"><span data-stu-id="9f30d-110">You can also use the **SaveFile** method to save data to a stream.</span></span> <span data-ttu-id="9f30d-111">有关详细信息，请参阅 <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>。</span><span class="sxs-lookup"><span data-stu-id="9f30d-111">For more information, see <xref:System.Windows.Forms.RichTextBox.SaveFile%28System.IO.Stream%2CSystem.Windows.Forms.RichTextBoxStreamType%29>.</span></span>  
  
### <a name="to-save-the-contents-of-the-control-to-a-file"></a><span data-ttu-id="9f30d-112">若要将控件的内容保存到文件</span><span class="sxs-lookup"><span data-stu-id="9f30d-112">To save the contents of the control to a file</span></span>  
  
1.  <span data-ttu-id="9f30d-113">确定要保存的文件的路径。</span><span class="sxs-lookup"><span data-stu-id="9f30d-113">Determine the path of the file to be saved.</span></span>  
  
     <span data-ttu-id="9f30d-114">若要执行此操作在实际应用程序中，通常可以使用<xref:System.Windows.Forms.SaveFileDialog>组件。</span><span class="sxs-lookup"><span data-stu-id="9f30d-114">To do this in a real-world application, you would typically use the <xref:System.Windows.Forms.SaveFileDialog> component.</span></span> <span data-ttu-id="9f30d-115">有关概述，请参阅[SaveFileDialog 组件概述](savefiledialog-component-overview-windows-forms.md)。</span><span class="sxs-lookup"><span data-stu-id="9f30d-115">For an overview, see [SaveFileDialog Component Overview](savefiledialog-component-overview-windows-forms.md).</span></span>  
  
2.  <span data-ttu-id="9f30d-116">调用<xref:System.Windows.Forms.RichTextBox.SaveFile%2A>方法的<xref:System.Windows.Forms.RichTextBox>控件，指定要保存的文件和文件类型 （可选）。</span><span class="sxs-lookup"><span data-stu-id="9f30d-116">Call the <xref:System.Windows.Forms.RichTextBox.SaveFile%2A> method of the <xref:System.Windows.Forms.RichTextBox> control, specifying the file to save and optionally a file type.</span></span> <span data-ttu-id="9f30d-117">如果调用使用文件名作为其唯一参数的方法，该文件将保存为 rtf 格式。</span><span class="sxs-lookup"><span data-stu-id="9f30d-117">If you call the method with a file name as its only argument, the file will be saved as RTF.</span></span> <span data-ttu-id="9f30d-118">若要指定其他文件类型，请使用 <xref:System.Windows.Forms.RichTextBoxStreamType> 枚举的值作为其第二个参数来调用该方法。</span><span class="sxs-lookup"><span data-stu-id="9f30d-118">To specify another file type, call the method with a value of the <xref:System.Windows.Forms.RichTextBoxStreamType> enumeration as its second argument.</span></span>  
  
     <span data-ttu-id="9f30d-119">在下面的示例中，将路径设置为格式文本文件的位置**我的文档**文件夹。</span><span class="sxs-lookup"><span data-stu-id="9f30d-119">In the example below, the path set for the location of the rich-text file is the **My Documents** folder.</span></span> <span data-ttu-id="9f30d-120">使用此位置是因为您可以假定大多数运行 Windows 操作系统的计算机将包含该文件夹。</span><span class="sxs-lookup"><span data-stu-id="9f30d-120">This location is used because you can assume that most computers running the Windows operating system will include this folder.</span></span> <span data-ttu-id="9f30d-121">选择此位置还允许具有最少的系统访问级别的用户安全地运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="9f30d-121">Choosing this location also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="9f30d-122">下面的示例假定窗体具有<xref:System.Windows.Forms.RichTextBox>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="9f30d-122">The example below assumes a form with a <xref:System.Windows.Forms.RichTextBox> control already added.</span></span>  
  
    ```vb  
    Public Sub SaveFile()  
       ' You should replace the bold file name in the   
       ' sample below with a file name of your own choosing.  
       RichTextBox1.SaveFile(System.Environment.GetFolderPath _  
       (System.Environment.SpecialFolder.Personal) _  
       & "\Testdoc.rtf", _  
          RichTextBoxStreamType.RichNoOleObjs)  
    End Sub  
    ```  
  
    ```csharp  
    public void SaveFile()  
    {  
       // You should replace the bold file name in the   
       // sample below with a file name of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       richTextBox1.SaveFile(System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Testdoc.rtf",  
          RichTextBoxStreamType.RichNoOleObjs);  
    }  
    ```  
  
    ```cpp  
    public:  
       void SaveFile()  
       {  
          // You should replace the bold file name in the   
          // sample below with a file name of your own choosing.  
          richTextBox1->SaveFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Testdoc.rtf"), RichTextBoxStreamType::RichNoOleObjs);  
       }  
    ```  
  
    > [!IMPORTANT]
    >  <span data-ttu-id="9f30d-123">此示例在文件尚未存在时创建新文件。</span><span class="sxs-lookup"><span data-stu-id="9f30d-123">This example creates a new file, if the file does not already exist.</span></span> <span data-ttu-id="9f30d-124">如果应用程序需要创建一个文件，该应用程序将需要的文件夹创建访问权限。</span><span class="sxs-lookup"><span data-stu-id="9f30d-124">If an application needs to create a file, that application needs Create access for the folder.</span></span> <span data-ttu-id="9f30d-125">可使用访问控制列表设置权限。</span><span class="sxs-lookup"><span data-stu-id="9f30d-125">Permissions are set using access control lists.</span></span> <span data-ttu-id="9f30d-126">如果该文件已存在，该应用程序需要只写访问权限，较弱的特权。</span><span class="sxs-lookup"><span data-stu-id="9f30d-126">If the file already exists, the application needs only Write access, a lesser privilege.</span></span> <span data-ttu-id="9f30d-127">在可能的情况下，会在部署期间，创建文件并仅授予对单个文件，读取访问权限而不是创建一个文件夹的访问更安全。</span><span class="sxs-lookup"><span data-stu-id="9f30d-127">Where possible, it is more secure to create the file during deployment, and only grant Read access to a single file, rather than Create access for a folder.</span></span> <span data-ttu-id="9f30d-128">此外，较安全的做法是将数据写入用户文件夹，而不是根文件夹或“Program Files”文件夹。</span><span class="sxs-lookup"><span data-stu-id="9f30d-128">Also, it is more secure to write data to user folders than to the root folder or the Program Files folder.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f30d-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="9f30d-129">See also</span></span>
- <xref:System.Windows.Forms.RichTextBox.SaveFile%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.RichTextBox>
- [<span data-ttu-id="9f30d-130">RichTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="9f30d-130">RichTextBox Control</span></span>](richtextbox-control-windows-forms.md)
- [<span data-ttu-id="9f30d-131">在 Windows 窗体上使用的控件</span><span class="sxs-lookup"><span data-stu-id="9f30d-131">Controls to Use on Windows Forms</span></span>](controls-to-use-on-windows-forms.md)
