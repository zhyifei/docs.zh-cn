---
title: Splitter 컨트롤 개요
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 3d6da8daf9bb0e8df4f69554a87725a7ddb65acb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742896"
---
# <a name="splitter-control-overview-windows-forms"></a>Splitter 컨트롤 개요(Windows Forms)
> [!IMPORTANT]
> 尽管 <xref:System.Windows.Forms.SplitContainer> 替换先前版本的 <xref:System.Windows.Forms.Splitter> 控件并添加功能，但如果你选择，将保留 <xref:System.Windows.Forms.Splitter> 以实现向后兼容性和将来使用。  
  
 Windows 窗体 <xref:System.Windows.Forms.Splitter> 控件用于在运行时调整停靠控件的大小。 <xref:System.Windows.Forms.Splitter> 控件通常用于具有具有不同数据长度的控件的窗体，如 Windows 资源管理器，其数据窗格在不同时间包含不同宽度的信息。  
  
## <a name="working-with-the-splitter-control"></a>使用拆分器控件  
 当用户将鼠标指针指向可通过拆分器控件调整大小的控件的未停靠边缘时，指针将更改其外观，以指示可调整控件的大小。 利用拆分器控件，用户可以重设紧靠其后的停靠控件的大小。 因此，若要使用户能够在运行时调整停靠控件的大小，请将调整大小的控件停靠到容器的边缘，然后将拆分器控件停靠到该容器的同一侧。  
  
## <a name="see-also"></a>另请参阅

- <xref:System.Windows.Forms.SplitContainer>
- [방법: Windows Forms에서 컨트롤 고정](how-to-dock-controls-on-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
