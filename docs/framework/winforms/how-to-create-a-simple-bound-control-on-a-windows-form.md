---
title: 如何：创建 Windows 窗体上的简单绑定控件
ms.date: 03/30/2017
helpviewer_keywords:
- data binding [Windows Forms], simple data binding
- Windows Forms controls, data binding
ms.assetid: 3bcaded8-0f1a-4cc0-8830-f59be253bf4e
ms.openlocfilehash: 129301354c67d43783e997bcf42f848c5c39ab3c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/23/2019
ms.locfileid: "54643567"
---
# <a name="how-to-create-a-simple-bound-control-on-a-windows-form"></a><span data-ttu-id="56084-102">如何：创建 Windows 窗体上的简单绑定控件</span><span class="sxs-lookup"><span data-stu-id="56084-102">How to: Create a Simple-Bound Control on a Windows Form</span></span>
<span data-ttu-id="56084-103">与*简单绑定*，可以在控件中显示单个数据元素，如从数据集表中列的值。</span><span class="sxs-lookup"><span data-stu-id="56084-103">With *simple binding*, you can display a single data element, such as a column value from a dataset table, in a control.</span></span> <span data-ttu-id="56084-104">可以将控件属性简单绑定到数据值。</span><span class="sxs-lookup"><span data-stu-id="56084-104">You can simple-bind any property of a control to a data value.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="56084-105">显示的对话框和菜单命令可能会与“帮助”中的描述不同，具体取决于你现用的设置或版本。</span><span class="sxs-lookup"><span data-stu-id="56084-105">The dialog boxes and menu commands you see might differ from those described in Help depending on your active settings or edition.</span></span> <span data-ttu-id="56084-106">若要更改设置，请在 **“工具”** 菜单上选择 **“导入和导出设置”** 。</span><span class="sxs-lookup"><span data-stu-id="56084-106">To change your settings, choose **Import and Export Settings** on the **Tools** menu.</span></span> <span data-ttu-id="56084-107">有关详细信息，请参阅[个性化设置 Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide)。</span><span class="sxs-lookup"><span data-stu-id="56084-107">For more information, see [Personalize the Visual Studio IDE](/visualstudio/ide/personalizing-the-visual-studio-ide).</span></span>  
  
### <a name="to-simple-bind-a-control"></a><span data-ttu-id="56084-108">简单绑定控件</span><span class="sxs-lookup"><span data-stu-id="56084-108">To simple-bind a control</span></span>  
  
1.  <span data-ttu-id="56084-109">连接到数据源。</span><span class="sxs-lookup"><span data-stu-id="56084-109">Connect to a data source.</span></span> <span data-ttu-id="56084-110">有关详细信息，请参阅[连接到数据源](../../../docs/framework/data/adonet/connecting-to-a-data-source.md)。</span><span class="sxs-lookup"><span data-stu-id="56084-110">For more information, see [Connecting to a Data Source](../../../docs/framework/data/adonet/connecting-to-a-data-source.md).</span></span>  
  
2.  <span data-ttu-id="56084-111">在表单中，选择控件并显示**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="56084-111">In the form, select the control and display the **Properties** window.</span></span>  
  
3.  <span data-ttu-id="56084-112">展开 **(DataBindings)** 属性。</span><span class="sxs-lookup"><span data-stu-id="56084-112">Expand the **(DataBindings)** property.</span></span>  
  
     <span data-ttu-id="56084-113">最常绑定的属性将显示下面 **(DataBindings)** 属性。</span><span class="sxs-lookup"><span data-stu-id="56084-113">The properties most often bound are displayed underneath the **(DataBindings)** property.</span></span> <span data-ttu-id="56084-114">例如，在大多数控件而言**文本**最经常绑定属性。</span><span class="sxs-lookup"><span data-stu-id="56084-114">For example, in most controls, the **Text** property is most frequently bound.</span></span>  
  
4.  <span data-ttu-id="56084-115">如果该属性要绑定不经常绑定的属性之一，请单击**省略号**按钮 (![VisualStudioEllipsesButton 屏幕快照](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) 中 **（高级）** 框，以显示**格式设置和高级绑定**为该控件的属性的完整列表对话框。</span><span class="sxs-lookup"><span data-stu-id="56084-115">If the property you want to bind is not one of the commonly bound properties, click the **Ellipsis** button (![VisualStudioEllipsesButton screenshot](../../../docs/framework/winforms/media/vbellipsesbutton.png "vbEllipsesButton")) in the **(Advanced)** box to display the **Formatting and Advanced Binding** dialog box with a complete list of properties for that control.</span></span>  
  
5.  <span data-ttu-id="56084-116">选择你想要绑定，并单击下的下拉箭头的属性**绑定**。</span><span class="sxs-lookup"><span data-stu-id="56084-116">Select the property you want to bind and click the drop-down arrow under **Binding**.</span></span>  
  
     <span data-ttu-id="56084-117">此时将显示可用数据源的列表。</span><span class="sxs-lookup"><span data-stu-id="56084-117">A list of available data sources is displayed.</span></span>  
  
6.  <span data-ttu-id="56084-118">展开要绑定到的数据源，直到找到所需的单个数据元素。</span><span class="sxs-lookup"><span data-stu-id="56084-118">Expand the data source you want to bind to until you find the single data element you want.</span></span> <span data-ttu-id="56084-119">例如，如果你正在绑定到数据集表中的列值，请展开该数据集的名称，然后展开表名以显示列名。</span><span class="sxs-lookup"><span data-stu-id="56084-119">For example, if you are binding to a column value in a dataset's table, expand the name of the dataset, and then expand the table name to display column names.</span></span>  
  
7.  <span data-ttu-id="56084-120">单击要绑定到的元素的名称。</span><span class="sxs-lookup"><span data-stu-id="56084-120">Click the name of an element to bind to.</span></span>  
  
8.  <span data-ttu-id="56084-121">如果您正在处理**格式设置和高级绑定**对话框中，单击**确定**回到**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="56084-121">If you were working in the **Formatting and Advanced Binding** dialog box, click **OK** to return to the **Properties** window.</span></span>  
  
9. <span data-ttu-id="56084-122">如果你想要将绑定控件的其他属性，请重复步骤 3 至 7。</span><span class="sxs-lookup"><span data-stu-id="56084-122">If you want to bind additional properties of the control, repeat steps 3 through 7.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="56084-123">由于简单绑定控件显示单个数据元素，它是非常典型，若要在具有简单绑定控件的 Windows 窗体中包含导航逻辑。</span><span class="sxs-lookup"><span data-stu-id="56084-123">Because simple-bound controls show only a single data element, it is very typical to include navigation logic in a Windows Form with simple-bound controls.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56084-124">请参阅</span><span class="sxs-lookup"><span data-stu-id="56084-124">See also</span></span>
- <xref:System.Windows.Forms.Binding>
- [<span data-ttu-id="56084-125">Windows 窗体数据绑定</span><span class="sxs-lookup"><span data-stu-id="56084-125">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
- [<span data-ttu-id="56084-126">数据绑定和 Windows 窗体</span><span class="sxs-lookup"><span data-stu-id="56084-126">Data Binding and Windows Forms</span></span>](../../../docs/framework/winforms/data-binding-and-windows-forms.md)
