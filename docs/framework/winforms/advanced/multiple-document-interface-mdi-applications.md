---
title: 多文档界面 (MDI) 应用程序
ms.date: 03/30/2017
helpviewer_keywords:
- forms [Windows Forms], MDI
- windows [Windows Forms], mDI
- Windows Forms, MDI applications
- MDI
ms.assetid: 599faf75-13cf-49cc-ad3c-255545e5cb97
ms.openlocfilehash: 23e0275d5e6b081ec02d669a78e8695453360637
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69956550"
---
# <a name="multiple-document-interface-mdi-applications"></a>多文档界面 (MDI) 应用程序
多文档界面 (MDI) 应用程序使您能够同时显示多个文档, 每个文档都显示在其自己的窗口中。 MDI 应用程序通常具有一个带有子菜单的 "窗口" 菜单项, 用于在窗口或文档之间进行切换。  
  
> [!NOTE]
> Windows 窗体中的 MDI 窗体和单文档界面 (SDI) 窗口之间存在一些行为差异。 `Opacity`属性不影响 MDI 子窗体的外观。 此外, 此<xref:System.Windows.Forms.Form.CenterToParent%2A>方法不会影响 MDI 子窗体的行为。  
  
## <a name="in-this-section"></a>本节内容  
 [如何：创建 MDI 父窗体](how-to-create-mdi-parent-forms.md)  
 提供有关为 MDI 应用程序中的多个文档创建容器的说明。  
  
 [如何：创建 MDI 子窗体](how-to-create-mdi-child-forms.md)  
 提供有关创建在 MDI 父窗体中运行的一个或多个窗口的说明。  
  
 [如何：确定活动的 MDI 子窗](how-to-determine-the-active-mdi-child.md)  
 为验证具有焦点的子窗口 (并将其内容发送到剪贴板) 提供说明。  
  
 [如何：将数据发送到活动的 MDI 子级](how-to-send-data-to-the-active-mdi-child.md)  
 提供将信息传输到活动子窗口的说明。  
  
 [如何：排列 MDI 子窗体](how-to-arrange-mdi-child-forms.md)  
 提供平铺、层叠或排列 MDI 应用程序的子窗口的说明。
