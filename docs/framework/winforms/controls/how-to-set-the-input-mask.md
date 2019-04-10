---
title: 如何：设置输入掩码
ms.date: 03/30/2017
f1_keywords:
- net.ComponentModel.MaskPropertyEditor
helpviewer_keywords:
- MaskedTextBox control [Windows Forms]
ms.assetid: 779b3a12-cd74-4e58-b46e-04983bda5b2c
ms.openlocfilehash: 14591b313b0ba4fc2a0a30a45c693147f00050b5
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207534"
---
# <a name="how-to-set-the-input-mask"></a><span data-ttu-id="9ec07-102">如何：设置输入掩码</span><span class="sxs-lookup"><span data-stu-id="9ec07-102">How to: Set the Input Mask</span></span>
<span data-ttu-id="9ec07-103">掩码的文本框控件是支持的声明性语法来接受或拒绝用户输入增强的文本框控件。</span><span class="sxs-lookup"><span data-stu-id="9ec07-103">The masked text box control is an enhanced text box control that supports a declarative syntax for accepting or rejecting user input.</span></span> <span data-ttu-id="9ec07-104">通过设置掩码属性，可以指定允许的用户输入，而无需在应用程序中编写任何自定义验证逻辑。</span><span class="sxs-lookup"><span data-stu-id="9ec07-104">By setting the Mask property, you can specify the allowable user input without writing any custom validation logic in your application.</span></span> <span data-ttu-id="9ec07-105">有关详细信息，请参阅备注部分的<xref:System.Windows.Forms.MaskedTextBox>类。</span><span class="sxs-lookup"><span data-stu-id="9ec07-105">For more information, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox> class.</span></span>  
  
## <a name="setting-the-mask-property-manually"></a><span data-ttu-id="9ec07-106">手动设置掩码属性</span><span class="sxs-lookup"><span data-stu-id="9ec07-106">Setting the Mask Property Manually</span></span>  
 <span data-ttu-id="9ec07-107">如果你熟悉使用掩码属性支持的字符，则可以手动输入它。</span><span class="sxs-lookup"><span data-stu-id="9ec07-107">If you are familiar with the characters that the Mask property supports, you can enter it manually.</span></span> <span data-ttu-id="9ec07-108">掩码属性支持的字符的摘要，请参阅备注部分的<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="9ec07-108">For a summary of the characters that the Mask property supports, see the Remarks section of the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
#### <a name="to-set-the-mask-property-manually"></a><span data-ttu-id="9ec07-109">若要手动设置掩码属性</span><span class="sxs-lookup"><span data-stu-id="9ec07-109">To set the Mask property manually</span></span>  
  
1.  <span data-ttu-id="9ec07-110">在中**设计**视图中，选择<xref:System.Windows.Forms.MaskedTextBox>。</span><span class="sxs-lookup"><span data-stu-id="9ec07-110">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
2.  <span data-ttu-id="9ec07-111">在中**属性**窗口中，找到<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="9ec07-111">In the **Properties** window, locate the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
3.  <span data-ttu-id="9ec07-112">键入所需的掩码。</span><span class="sxs-lookup"><span data-stu-id="9ec07-112">Type the mask that you want.</span></span> <span data-ttu-id="9ec07-113">例如，键入 `###`。</span><span class="sxs-lookup"><span data-stu-id="9ec07-113">For example, type `###`.</span></span>  
  
## <a name="using-the-input-mask-dialog-box"></a><span data-ttu-id="9ec07-114">使用输入的掩码对话框</span><span class="sxs-lookup"><span data-stu-id="9ec07-114">Using the Input Mask Dialog Box</span></span>  
 <span data-ttu-id="9ec07-115">输入掩码对话框中提供了一些预定义的输入的掩码。</span><span class="sxs-lookup"><span data-stu-id="9ec07-115">The Input Mask dialog box provides some predefined input masks.</span></span> <span data-ttu-id="9ec07-116">此外可以更改的预定义的掩码或手动输入自己的掩码。</span><span class="sxs-lookup"><span data-stu-id="9ec07-116">You can also change the predefined masks or enter your own mask manually.</span></span>  
  
#### <a name="to-open-the-input-mask-dialog-box"></a><span data-ttu-id="9ec07-117">若要打开输入掩码对话框</span><span class="sxs-lookup"><span data-stu-id="9ec07-117">To open the Input Mask dialog box</span></span>  
  
1.  <span data-ttu-id="9ec07-118">在中**设计**视图中，选择<xref:System.Windows.Forms.MaskedTextBox>。</span><span class="sxs-lookup"><span data-stu-id="9ec07-118">In **Design** view, select a <xref:System.Windows.Forms.MaskedTextBox>.</span></span>  
  
    1.  <span data-ttu-id="9ec07-119">单击要打开的智能标记**MaskedTextBox 任务**面板。</span><span class="sxs-lookup"><span data-stu-id="9ec07-119">Click the smart tag to open the **MaskedTextBox Tasks** panel.</span></span>  
  
    2.  <span data-ttu-id="9ec07-120">单击**设置掩码**。</span><span class="sxs-lookup"><span data-stu-id="9ec07-120">Click **Set Mask**.</span></span>  
  
     <span data-ttu-id="9ec07-121">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="9ec07-121">\- or -</span></span>  
  
    1.  <span data-ttu-id="9ec07-122">在中**属性**窗口中，选择<xref:System.Windows.Forms.MaskedTextBox.Mask%2A>属性。</span><span class="sxs-lookup"><span data-stu-id="9ec07-122">In the **Properties** window, select the <xref:System.Windows.Forms.MaskedTextBox.Mask%2A> property.</span></span>  
  
    2.  <span data-ttu-id="9ec07-123">单击属性值列中的省略号按钮。</span><span class="sxs-lookup"><span data-stu-id="9ec07-123">Click the ellipsis button in the property value column.</span></span>  
  
     <span data-ttu-id="9ec07-124">**输入掩码**对话框随即出现。</span><span class="sxs-lookup"><span data-stu-id="9ec07-124">The **Input Mask** dialog box appears.</span></span>  
  
#### <a name="to-use-the-input-mask-dialog-box"></a><span data-ttu-id="9ec07-125">若要使用输入掩码对话框</span><span class="sxs-lookup"><span data-stu-id="9ec07-125">To use the Input Mask dialog box</span></span>  
  
1.  <span data-ttu-id="9ec07-126">（可选）单击其中一个列表中的预定义掩码。</span><span class="sxs-lookup"><span data-stu-id="9ec07-126">(Optional) Click one of the predefined masks in the list.</span></span>  
  
2.  <span data-ttu-id="9ec07-127">（可选）编辑中的预定义的掩码**掩码**框。</span><span class="sxs-lookup"><span data-stu-id="9ec07-127">(Optional) Edit the predefined mask in the **Mask** box.</span></span>  
  
3.  <span data-ttu-id="9ec07-128">（可选）输入新掩码**掩码**框。</span><span class="sxs-lookup"><span data-stu-id="9ec07-128">(Optional) Type a new mask in the **Mask** box.</span></span> <span data-ttu-id="9ec07-129">也就是说，无需使用一个预定义的掩码。</span><span class="sxs-lookup"><span data-stu-id="9ec07-129">That is, you do not have to use one of the predefined masks.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="9ec07-130">预览框中会显示在用户将看到的字符<xref:System.Windows.Forms.MaskedTextBox>。</span><span class="sxs-lookup"><span data-stu-id="9ec07-130">The Preview box displays the characters that the user sees in the <xref:System.Windows.Forms.MaskedTextBox>.</span></span> <span data-ttu-id="9ec07-131">这些字符是指南可帮助用户正确输入数据。</span><span class="sxs-lookup"><span data-stu-id="9ec07-131">These characters are a guide to help the user enter the data correctly.</span></span>  
  
4.  <span data-ttu-id="9ec07-132">选中或清除**使用 ValidatingType**复选框。</span><span class="sxs-lookup"><span data-stu-id="9ec07-132">Select or clear the **Use ValidatingType** check box.</span></span> <span data-ttu-id="9ec07-133">**使用 ValidatingType**复选框指定是否一种数据类型用于验证输入的数据由用户。</span><span class="sxs-lookup"><span data-stu-id="9ec07-133">The **Use ValidatingType** check box specifies whether a data type is used to verify the data input by the user.</span></span> <span data-ttu-id="9ec07-134">有关更多信息，请参见 <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> 属性。</span><span class="sxs-lookup"><span data-stu-id="9ec07-134">For more information, see the <xref:System.Windows.Forms.MaskedTextBox.ValidatingType%2A> property.</span></span>  
  
5.  <span data-ttu-id="9ec07-135">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="9ec07-135">Click **OK**.</span></span>  
  
     <span data-ttu-id="9ec07-136">输入掩码**掩码**属性中的**属性**窗口。</span><span class="sxs-lookup"><span data-stu-id="9ec07-136">The mask is entered in the **Mask** property in the **Properties** window.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ec07-137">请参阅</span><span class="sxs-lookup"><span data-stu-id="9ec07-137">See also</span></span>

- [<span data-ttu-id="9ec07-138">演练：使用 MaskedTextBox 控件</span><span class="sxs-lookup"><span data-stu-id="9ec07-138">Walkthrough: Working with the MaskedTextBox Control</span></span>](walkthrough-working-with-the-maskedtextbox-control.md)
