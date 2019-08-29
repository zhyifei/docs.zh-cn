---
title: Splitter 控件概述（Windows 窗体）
ms.date: 03/30/2017
f1_keywords:
- Splitter
helpviewer_keywords:
- Splitter control [Windows Forms], about Splitter control
ms.assetid: e2b6ab83-dfdd-40ec-9762-850702c82dcb
ms.openlocfilehash: 934efd707f2a52da5ba604139c8e4510aad4606b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964462"
---
# <a name="splitter-control-overview-windows-forms"></a>Splitter 控件概述（Windows 窗体）
> [!IMPORTANT]
> 尽管<xref:System.Windows.Forms.SplitContainer>替换并添加了以前版本<xref:System.Windows.Forms.Splitter>的控件的功能, <xref:System.Windows.Forms.Splitter>但如果你选择, 将保留以实现向后兼容性和将来使用。  
  
 Windows 窗体<xref:System.Windows.Forms.Splitter>控件用于在运行时调整停靠控件的大小。 <xref:System.Windows.Forms.Splitter>控件通常用在具有不同的数据长度 (如 Windows 资源管理器) 的窗体上, 其数据窗格包含不同时间的不同宽度的信息。  
  
## <a name="working-with-the-splitter-control"></a>使用拆分器控件  
 当用户将鼠标指针指向可通过拆分器控件调整大小的控件的未停靠边缘时, 指针将更改其外观, 以指示可调整控件的大小。 利用拆分器控件, 用户可以重设紧靠其后的停靠控件的大小。 因此, 若要使用户能够在运行时调整停靠控件的大小, 请将调整大小的控件停靠到容器的边缘, 然后将拆分器控件停靠到该容器的同一侧。  
  
## <a name="see-also"></a>请参阅

- <xref:System.Windows.Forms.SplitContainer>
- [如何：在 Windows 窗体上停靠控件](how-to-dock-controls-on-windows-forms.md)
- [在 Windows 窗体上使用的控件](controls-to-use-on-windows-forms.md)
