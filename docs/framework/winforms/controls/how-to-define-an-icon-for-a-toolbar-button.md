---
title: 如何：定义的工具栏按钮的图标
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- toolbars [Windows Forms], adding icons to buttons
- buttons [Windows Forms], icons
- examples [Windows Forms], toolbars
- images [Windows Forms], toolbar buttons
- icons [Windows Forms], toolbar buttons
- ToolBar control [Windows Forms], adding icons to buttons
ms.assetid: 84db98b4-8566-49ce-b2c8-1fd66a5eb3a0
ms.openlocfilehash: fa622245155a1e7bdeb0184b0cd5ff07f651bfbc
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54644789"
---
# <a name="how-to-define-an-icon-for-a-toolbar-button"></a><span data-ttu-id="e2b32-102">如何：定义的工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="e2b32-102">How to: Define an Icon for a ToolBar Button</span></span>
> [!NOTE]
>  <span data-ttu-id="e2b32-103"><xref:System.Windows.Forms.ToolStrip> 控件取代了 <xref:System.Windows.Forms.ToolBar> 控件并添加了功能；但是，可以选择保留 <xref:System.Windows.Forms.ToolBar> 控件以实现向后兼容并供将来使用。</span><span class="sxs-lookup"><span data-stu-id="e2b32-103">The <xref:System.Windows.Forms.ToolStrip> control replaces and adds functionality to the <xref:System.Windows.Forms.ToolBar> control; however, the <xref:System.Windows.Forms.ToolBar> control is retained for both backward compatibility and future use, if you choose.</span></span>  
  
 <span data-ttu-id="e2b32-104"><xref:System.Windows.Forms.ToolBar> 按钮是可以由用户显示其中方便识别的图标。</span><span class="sxs-lookup"><span data-stu-id="e2b32-104"><xref:System.Windows.Forms.ToolBar> buttons are able to display icons within them for easy identification by users.</span></span> <span data-ttu-id="e2b32-105">这通过添加到图像[ImageList 组件](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)组件并将相关联<xref:System.Windows.Forms.ImageList>组件与<xref:System.Windows.Forms.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="e2b32-105">This is achieved through adding images to the [ImageList Component](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md) component and then associating the <xref:System.Windows.Forms.ImageList> component with the <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
### <a name="to-set-an-icon-for-a-toolbar-button-programmatically"></a><span data-ttu-id="e2b32-106">若要以编程方式设置工具栏按钮的图标</span><span class="sxs-lookup"><span data-stu-id="e2b32-106">To set an icon for a toolbar button programmatically</span></span>  
  
1.  <span data-ttu-id="e2b32-107">在过程中，实例化<xref:System.Windows.Forms.ImageList>组件和一个<xref:System.Windows.Forms.ToolBar>控件。</span><span class="sxs-lookup"><span data-stu-id="e2b32-107">In a procedure, instantiate an <xref:System.Windows.Forms.ImageList> component and a <xref:System.Windows.Forms.ToolBar> control.</span></span>  
  
2.  <span data-ttu-id="e2b32-108">在相同的过程中，将分配到图像<xref:System.Windows.Forms.ImageList>组件。</span><span class="sxs-lookup"><span data-stu-id="e2b32-108">In the same procedure, assign an image to the <xref:System.Windows.Forms.ImageList> component.</span></span>  
  
3.  <span data-ttu-id="e2b32-109">在相同的过程中，将分配<xref:System.Windows.Forms.ImageList>控制对<xref:System.Windows.Forms.ToolBar>控件并将分配<xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A>各个工具栏按钮的属性。</span><span class="sxs-lookup"><span data-stu-id="e2b32-109">In the same procedure, assign the <xref:System.Windows.Forms.ImageList> control to the <xref:System.Windows.Forms.ToolBar> control and assign the <xref:System.Windows.Forms.ToolBarButton.ImageIndex%2A> property of the individual toolbar buttons.</span></span>  
  
     <span data-ttu-id="e2b32-110">在下面的代码示例中，将路径设置的映像的位置是**我的文档**文件夹。</span><span class="sxs-lookup"><span data-stu-id="e2b32-110">In the following code example, the path set for the location of the image is the **My Documents** folder.</span></span> <span data-ttu-id="e2b32-111">此操作后，因为您可以假定大多数运行 Windows 操作系统的计算机都包含此目录。</span><span class="sxs-lookup"><span data-stu-id="e2b32-111">This is done, because you can assume that most computers running the Windows operating system will include this directory.</span></span> <span data-ttu-id="e2b32-112">这还使得具有最低系统访问级别的用户能够安全运行应用程序。</span><span class="sxs-lookup"><span data-stu-id="e2b32-112">This also allows users with minimal system access levels to safely run the application.</span></span> <span data-ttu-id="e2b32-113">下面的示例假定窗体具有<xref:System.Windows.Forms.PictureBox>已添加的控件。</span><span class="sxs-lookup"><span data-stu-id="e2b32-113">The example below assumes a form with a <xref:System.Windows.Forms.PictureBox> control already added.</span></span>  
  
     <span data-ttu-id="e2b32-114">按照上述步骤中，您应编写类似于下面显示的代码。</span><span class="sxs-lookup"><span data-stu-id="e2b32-114">Following the steps above, you should have written code similar to that displayed below.</span></span>  
  
    ```vb  
    Public Sub InitializeMyToolBar()  
    ' Instantiate an ImageList component and a ToolBar control.  
       Dim ToolBar1 as New ToolBar  
       Dim ImageList1 as New ImageList  
    ' Assign an image to the ImageList component.  
    ' You should replace the bold image  
    ' in the sample below with an icon of your own choosing.  
       Dim myImage As System.Drawing.Image = _   
          Image.FromFile Image.FromFile _  
          (System.Environment.GetFolderPath _  
          (System.Environment.SpecialFolder.Personal) _  
          & "\Image.gif")  
       ImageList1.Images.Add(myImage)  
    ' Create a ToolBarButton.  
       Dim ToolBarButton1 As New ToolBarButton()  
    ' Add the ToolBarButton to the ToolBar.  
       ToolBar1.Buttons.Add(toolBarButton1)  
    ' Assign an ImageList to the ToolBar.  
       ToolBar1.ImageList = ImageList1  
    ' Assign the ImageIndex property of the ToolBarButton.  
       ToolBarButton1.ImageIndex = 0  
    End Sub  
    ```  
  
    ```csharp  
    public void InitializeMyToolBar()  
    {  
       // Instantiate an ImageList component and a ToolBar control.  
       ToolBar toolBar1 = new  ToolBar();   
       ImageList imageList1 = new ImageList();  
       // Assign an image to the ImageList component.  
       // You should replace the bold image   
       // in the sample below with an icon of your own choosing.  
       // Note the escape character used (@) when specifying the path.  
       Image myImage = Image.FromFile  
       (System.Environment.GetFolderPath  
       (System.Environment.SpecialFolder.Personal)  
       + @"\Image.gif");  
       imageList1.Images.Add(myImage);  
       // Create a ToolBarButton.  
       ToolBarButton toolBarButton1 = new ToolBarButton();  
       // Add the ToolBarButton to the ToolBar.  
       toolBar1.Buttons.Add(toolBarButton1);  
       // Assign an ImageList to the ToolBar.  
       toolBar1.ImageList = imageList1;  
       // Assign ImageIndex property of the ToolBarButton.  
       toolBarButton1.ImageIndex = 0;  
    }  
    ```  
  
    ```cpp  
    public:  
       void InitializeMyToolBar()  
       {  
          // Instantiate an ImageList component and a ToolBar control.  
          ToolBar ^ toolBar1 = gcnew  ToolBar();   
          ImageList ^ imageList1 = gcnew ImageList();  
          // Assign an image to the ImageList component.  
          // You should replace the bold image   
          // in the sample below with an icon of your own choosing.  
          Image ^ myImage = Image::FromFile(String::Concat  
             (System::Environment::GetFolderPath  
             (System::Environment::SpecialFolder::Personal),  
             "\\Image.gif"));  
          imageList1->Images->Add(myImage);  
          // Create a ToolBarButton.  
          ToolBarButton ^ toolBarButton1 = gcnew ToolBarButton();  
          // Add the ToolBarButton to the ToolBar.  
          toolBar1->Buttons->Add(toolBarButton1);  
          // Assign an ImageList to the ToolBar.  
          toolBar1->ImageList = imageList1;  
          // Assign ImageIndex property of the ToolBarButton.  
          toolBarButton1->ImageIndex = 0;  
       }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="e2b32-115">请参阅</span><span class="sxs-lookup"><span data-stu-id="e2b32-115">See also</span></span>
- <xref:System.Windows.Forms.ToolBar>
- [<span data-ttu-id="e2b32-116">如何：触发工具栏按钮的菜单事件</span><span class="sxs-lookup"><span data-stu-id="e2b32-116">How to: Trigger Menu Events for Toolbar Buttons</span></span>](../../../../docs/framework/winforms/controls/how-to-trigger-menu-events-for-toolbar-buttons.md)
- [<span data-ttu-id="e2b32-117">ToolBar 控件</span><span class="sxs-lookup"><span data-stu-id="e2b32-117">ToolBar Control</span></span>](../../../../docs/framework/winforms/controls/toolbar-control-windows-forms.md)
- [<span data-ttu-id="e2b32-118">ImageList 组件</span><span class="sxs-lookup"><span data-stu-id="e2b32-118">ImageList Component</span></span>](../../../../docs/framework/winforms/controls/imagelist-component-windows-forms.md)
