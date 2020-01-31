---
title: 控件的辅助功能属性
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms, accessibility properties of controls
- accessibility [Windows Forms], Windows Forms control properties
ms.assetid: ad3567a6-313b-4708-9e15-f487a831f049
ms.openlocfilehash: 73d81f5b5f656ed5ef90bdd9b6fe1b3293123f97
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743427"
---
# <a name="properties-on-windows-forms-controls-that-support-accessibility-guidelines"></a>내게 필요한 옵션 지침을 지원하는 Windows Forms 컨트롤의 속성
Windows 窗体的标准工具箱中的控件支持许多辅助功能准则，包括公开键盘焦点并公开屏幕元素。  
  
## <a name="planning-ahead-for-accessibility"></a>提前规划辅助功能  
 控件的属性可用于支持其他辅助功能准则，如下表所示。 此外，还应使用菜单提供对程序功能的访问权限。  
  
|控件属性|辅助功能注意事项|  
|----------------------|--------------------------------------|  
|AccessibleDescription|描述将报告给辅助工具，如屏幕阅读器。 접근성 보조 기능은 장애가 있는 사용자가 컴퓨터를 보다 효율적으로 사용하도록 돕는 특수 프로그램 및 디바이스입니다.|  
|AccessibleName|将报告给辅助功能辅助工具的名称。|  
|AccessibleRole|介绍如何在用户界面中使用元素。|  
|TabIndex|通过窗体创建一个明智的导航路径。 对于没有内部标签的控件（如文本框），要使它们的关联标签在 tab 键顺序中紧挨着，这一点非常重要。|  
|텍스트|使用 "&" 字符创建访问密钥。 使用访问密钥是提供对功能的已记录的键盘访问。|  
|글꼴 크기|如果字体大小不可调整，则应将其设置为10磅或更大。 设置窗体的字体大小后，此后添加到窗体的所有控件都将具有相同的大小。|  
|Forecolor|如果将此属性设置为默认值，则将在窗体上使用用户的颜色首选项。|  
|Backcolor|如果将此属性设置为默认值，则将在窗体上使用用户的颜色首选项。|  
|BackgroundImage|将此属性留空可使文本更具可读性。|  
  
## <a name="see-also"></a>另请参阅

- [연습: 내게 필요한 옵션이 지원되는 Windows 기반 애플리케이션 만들기](walkthrough-creating-an-accessible-windows-based-application.md)
