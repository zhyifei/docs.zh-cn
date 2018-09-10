---
title: 在 XNA 应用程序中使用操作和惯性
ms.date: 03/30/2017
ms.assetid: b7c18905-850c-4da4-8977-a074406a4263
ms.openlocfilehash: 70b8d0c5c098089b6f16ef817ff86698f68cf7c3
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2018
ms.locfileid: "44248899"
---
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a><span data-ttu-id="b4bfa-102">在 XNA 应用程序中使用操作和惯性</span><span class="sxs-lookup"><span data-stu-id="b4bfa-102">Using Manipulations and Inertia in an XNA Application</span></span>
<span data-ttu-id="b4bfa-103">本文介绍如何在 Microsoft XNA 应用程序中使用操作和惯性处理来控制游戏块的移动。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-103">This article describes how you can use manipulations and inertia processing in a Microsoft XNA application to control the movement of game pieces.</span></span> <span data-ttu-id="b4bfa-104">在阅读本文之前，应熟悉[操作和惯性概述](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)主题以及基本的 XNA 编程概念。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-104">Before you read this article, you should be familiar with the [Manipulations and Inertia Overview](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md) topic, and be familiar with basic XNA programming concepts.</span></span>  
  
 <span data-ttu-id="b4bfa-105">若要执行本文所述的任务，你的 XNA 项目必须引用 <xref:System.Windows.Input.Manipulations> 程序集，且必须在计算机上安装 [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx)（[下载地址](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)），这样你的项目才可以引用 XNA 程序集。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-105">To perform the tasks described in this article, your XNA project must reference the <xref:System.Windows.Input.Manipulations> assembly, and you must have [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx) ([download](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)) installed on your computer so that your project can reference the XNA assemblies.</span></span>  
  
## <a name="overview-of-functionality"></a><span data-ttu-id="b4bfa-106">功能概述</span><span class="sxs-lookup"><span data-stu-id="b4bfa-106">Overview of Functionality</span></span>  
 <span data-ttu-id="b4bfa-107">本文介绍了如何创建表示游戏块（该游戏块使用操作和惯性处理）的自定义类。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-107">This article shows you how to create a custom class that represents a game piece that uses manipulation and inertia processing.</span></span> <span data-ttu-id="b4bfa-108">此类使你能通过用鼠标拖动然后释放游戏块，在屏幕上操作游戏块。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-108">This class enables you to manipulate a game piece across the screen by dragging it with the mouse, and then releasing it.</span></span> <span data-ttu-id="b4bfa-109">一旦释放，惯性处理在游戏块逐渐减速的过程中使其保持移动。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-109">Once released, inertia processing keeps the game piece moving as it gradually slows down.</span></span> <span data-ttu-id="b4bfa-110">移动是线性的和具有角度的。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-110">Movement is both linear and angular.</span></span>  
  
 <span data-ttu-id="b4bfa-111">![一个简单的操作和惯性应用程序。](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span><span class="sxs-lookup"><span data-stu-id="b4bfa-111">![A simple manipulations and inertia application.](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")</span></span>  
  
 <span data-ttu-id="b4bfa-112">此外，创建了一个自定义集合，用于管理多个游戏块。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-112">In addition, a custom collection is created that manages multiple game pieces.</span></span> <span data-ttu-id="b4bfa-113">这简化了 XNA 游戏类所需的处理。</span><span class="sxs-lookup"><span data-stu-id="b4bfa-113">This simplifies the handling that is required from the XNA Game class.</span></span>  
  
 [<span data-ttu-id="b4bfa-114">创建 GamePiece 类</span><span class="sxs-lookup"><span data-stu-id="b4bfa-114">Creating the GamePiece Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [<span data-ttu-id="b4bfa-115">创建 GamePieceCollection 类</span><span class="sxs-lookup"><span data-stu-id="b4bfa-115">Creating the GamePieceCollection Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [<span data-ttu-id="b4bfa-116">创建 Game1 类</span><span class="sxs-lookup"><span data-stu-id="b4bfa-116">Creating the Game1 Class</span></span>](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [<span data-ttu-id="b4bfa-117">完整代码清单</span><span class="sxs-lookup"><span data-stu-id="b4bfa-117">Full Code Listings</span></span>](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a><span data-ttu-id="b4bfa-118">请参阅</span><span class="sxs-lookup"><span data-stu-id="b4bfa-118">See Also</span></span>  
 <xref:System.Windows.Input.Manipulations>  
 [<span data-ttu-id="b4bfa-119">控制和惯性概述</span><span class="sxs-lookup"><span data-stu-id="b4bfa-119">Manipulations and Inertia Overview</span></span>](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
