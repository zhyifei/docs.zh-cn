---
title: 如何：创建包含图像的按钮
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Button controls [WPF], creating
ms.assetid: 607a193c-4098-4dd8-8dc0-51256cec2020
ms.openlocfilehash: 5be928ac75ad727feabcde07ac0c6dc76ed130e6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61910944"
---
# <a name="how-to-create-a-button-that-has-an-image"></a><span data-ttu-id="febd0-102">如何：创建包含图像的按钮</span><span class="sxs-lookup"><span data-stu-id="febd0-102">How to: Create a Button That Has an Image</span></span>
<span data-ttu-id="febd0-103">此示例演示如何上包含一个图像<xref:System.Windows.Controls.Button>。</span><span class="sxs-lookup"><span data-stu-id="febd0-103">This example shows how to include an image on a <xref:System.Windows.Controls.Button>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="febd0-104">示例</span><span class="sxs-lookup"><span data-stu-id="febd0-104">Example</span></span>  
 <span data-ttu-id="febd0-105">下面的示例创建两个<xref:System.Windows.Controls.Button>控件。</span><span class="sxs-lookup"><span data-stu-id="febd0-105">The following example creates two <xref:System.Windows.Controls.Button> controls.</span></span> <span data-ttu-id="febd0-106">一个<xref:System.Windows.Controls.Button>包含文本，另一个包含图像。</span><span class="sxs-lookup"><span data-stu-id="febd0-106">One <xref:System.Windows.Controls.Button> contains text and the other contains an image.</span></span> <span data-ttu-id="febd0-107">映像是在一个名为数据，这是该示例的项目文件夹的子文件夹中。</span><span class="sxs-lookup"><span data-stu-id="febd0-107">The image is in a folder called data, which is a subfolder of the example’s project folder.</span></span> <span data-ttu-id="febd0-108">当用户单击<xref:System.Windows.Controls.Button>具有图像、 背景和其他文本<xref:System.Windows.Controls.Button>更改。</span><span class="sxs-lookup"><span data-stu-id="febd0-108">When a user clicks the <xref:System.Windows.Controls.Button> that has the image, the background and the text of the other <xref:System.Windows.Controls.Button> change.</span></span>  
  
 <span data-ttu-id="febd0-109">此示例将创建<xref:System.Windows.Controls.Button>通过使用标记控制，但使用代码来编写<xref:System.Windows.Controls.Primitives.ButtonBase.Click>事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="febd0-109">This example creates <xref:System.Windows.Controls.Button> controls by using markup but uses code to write the <xref:System.Windows.Controls.Primitives.ButtonBase.Click> event handlers.</span></span>  
  
 [!code-xaml[BtnColor#4](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml#4)]  
  
 [!code-csharp[BtnColor#6](~/samples/snippets/csharp/VS_Snippets_Wpf/BtnColor/CSharp/Pane1.xaml.cs#6)]
 [!code-vb[BtnColor#6](~/samples/snippets/visualbasic/VS_Snippets_Wpf/BtnColor/VisualBasic/Pane1.xaml.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="febd0-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="febd0-110">See also</span></span>

- [<span data-ttu-id="febd0-111">控件</span><span class="sxs-lookup"><span data-stu-id="febd0-111">Controls</span></span>](index.md)
- [<span data-ttu-id="febd0-112">控件库</span><span class="sxs-lookup"><span data-stu-id="febd0-112">Control Library</span></span>](control-library.md)
