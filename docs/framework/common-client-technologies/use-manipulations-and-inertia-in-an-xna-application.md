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
# <a name="using-manipulations-and-inertia-in-an-xna-application"></a>在 XNA 应用程序中使用操作和惯性
本文介绍如何在 Microsoft XNA 应用程序中使用操作和惯性处理来控制游戏块的移动。 在阅读本文之前，应熟悉[操作和惯性概述](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)主题以及基本的 XNA 编程概念。  
  
 若要执行本文所述的任务，你的 XNA 项目必须引用 <xref:System.Windows.Input.Manipulations> 程序集，且必须在计算机上安装 [XNA Game Studio](https://msdn.microsoft.com/library/bb200104.aspx)（[下载地址](https://www.microsoft.com/downloads/details.aspx?FamilyId=7D70D6ED-1EDD-4852-9883-9A33C0AD8FEE&displaylang=en)），这样你的项目才可以引用 XNA 程序集。  
  
## <a name="overview-of-functionality"></a>功能概述  
 本文介绍了如何创建表示游戏块（该游戏块使用操作和惯性处理）的自定义类。 此类使你能通过用鼠标拖动然后释放游戏块，在屏幕上操作游戏块。 一旦释放，惯性处理在游戏块逐渐减速的过程中使其保持移动。 移动是线性的和具有角度的。  
  
 ![一个简单的操作和惯性应用程序。](../../../docs/framework/common-client-technologies/media/ndp-gamexna.jpg "NDP_GameXna")  
  
 此外，创建了一个自定义集合，用于管理多个游戏块。 这简化了 XNA 游戏类所需的处理。  
  
 [创建 GamePiece 类](../../../docs/framework/common-client-technologies/creating-the-gamepiece-class.md)  
  
 [创建 GamePieceCollection 类](../../../docs/framework/common-client-technologies/creating-the-gamepiececollection-class.md)  
  
 [创建 Game1 类](../../../docs/framework/common-client-technologies/creating-the-game1-class.md)  
  
 [完整代码清单](../../../docs/framework/common-client-technologies/full-code-listings.md)  
  
## <a name="see-also"></a>请参阅  
 <xref:System.Windows.Input.Manipulations>  
 [控制和惯性概述](../../../docs/framework/common-client-technologies/manipulations-and-inertia-overview.md)
