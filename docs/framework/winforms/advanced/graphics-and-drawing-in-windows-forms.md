---
title: 图形和绘图
ms.date: 03/30/2017
helpviewer_keywords:
- graphics [Windows Forms]
- graphics [Windows Forms], using in Windows Forms
- GDI+, using in managed code
- drawing [Windows Forms]
ms.assetid: 362532c5-1a06-4257-bdc8-723461009ede
ms.openlocfilehash: 10ad18d38c84f6e447601ab6c8bf1a953dabb7cf
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746401"
---
# <a name="graphics-and-drawing-in-windows-forms"></a>Windows Forms의 그래픽 및 그리기
公共语言运行时使用名为 GDI + 的 Windows 图形设备接口（GDI）的高级实现。 利用 GDI +，你可以创建图形、绘制文本以及将图形图像作为对象进行操作。 GDI + 旨在提供性能和易用性。 可以使用 GDI + 在 Windows 窗体和控件上呈现图形图像。 尽管不能直接在 Web 窗体上使用 GDI +，但你可以通过图像 Web 服务器控件显示图形图像。  
  
 在本部分中，你将找到介绍 GDI + 编程基础知识的主题。 포괄적인 참조는 아니지만 이 섹션은 <xref:System.Drawing.Graphics>, <xref:System.Drawing.Pen>, <xref:System.Drawing.Brush> 및 <xref:System.Drawing.Color> 개체에 대한 정보를 포함하며 도형 그리기, 텍스트 그리기 또는 이미지 표시와 같은 작업을 수행하는 방법을 설명합니다. 有关详细信息，请参阅[Gdi + Reference](/windows/desktop/gdiplus/-gdiplus-class-gdi-reference)。  
  
 바로 시작하려면 [그래픽 프로그래밍 시작](getting-started-with-graphics-programming.md)을 참조하세요. Windows Forms에서 코드를 사용하여 선, 도형, 텍스트 등을 그리는 방법에 대한 항목이 있습니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [그래픽 개요](graphics-overview-windows-forms.md)  
 그래픽 관련 관리되는 클래스를 소개합니다.  
  
 [GDI + 관리 코드 정보](about-gdi-managed-code.md)  
 提供有关托管 GDI + 类的信息。  
  
 [관리되는 그래픽 클래스 사용](using-managed-graphics-classes.md)  
 演示如何使用 GDI + 托管类完成各种任务。  
  
## <a name="reference"></a>참조  
 <xref:System.Drawing>  
 提供对 GDI + 基本图形功能的访问权限。  
  
 <xref:System.Drawing.Drawing2D>  
 고급 2D 및 벡터 그래픽 기능을 제공합니다.  
  
 <xref:System.Drawing.Imaging>  
 提供高级 GDI + 图像处理功能。  
  
 <xref:System.Drawing.Text>  
 提供高级 GDI + 版式功能。 이 네임스페이스의 클래스를 통해 글꼴 컬렉션을 만들고 사용할 수 있습니다.  
  
 <xref:System.Drawing.Printing>  
 인쇄 기능을 제공합니다.  
  
## <a name="related-sections"></a>관련 섹션  
 [사용자 지정 컨트롤 그리기 및 렌더링](../controls/custom-control-painting-and-rendering.md)  
 컨트롤을 그리기 위한 코드를 제공하는 방법을 자세히 설명합니다.
