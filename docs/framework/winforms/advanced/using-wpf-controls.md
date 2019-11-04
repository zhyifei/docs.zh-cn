---
title: 使用 WPF 控件
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: jillre
ms.author: jillfra
manager: jillfra
ms.openlocfilehash: e9883e9d31fc9e3e2ec3ca06b4fc830bcdc338ae
ms.sourcegitcommit: 944ddc52b7f2632f30c668815f92b378efd38eea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2019
ms.locfileid: "73460691"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a>在 Windows 窗体应用中使用 WPF 控件

您可以在基于 Windows 窗体的应用程序中使用 Windows Presentation Foundation （WPF）控件。 尽管这是两种不同的视图技术，但它们可以顺畅地互操作。

Visual Studio 中的 Windows 窗体设计器提供了用于承载 Windows Presentation Foundation 控件的可视化设计环境。 WPF 控件由名为 <xref:System.Windows.Forms.Integration.ElementHost>的特殊 Windows 窗体控件承载。 此控件允许 WPF 控件参与窗体的布局以及接收键盘和鼠标消息。 在设计时，您可以像对任何 Windows 窗体控件一样排列 <xref:System.Windows.Forms.Integration.ElementHost> 控件。

你还可以在基于 WPF 的应用程序中使用 Windows 窗体控件。 有关详细信息，请参阅[在 Visual Studio 中设计 XAML](/visualstudio/xaml-tools/designing-xaml-in-visual-studio)。

## <a name="see-also"></a>请参阅

- [WPF 和 Windows 窗体互操作](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
