---
title: "使用自定义活动"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7558ca965af6cc9acd35ecab47bf9f66f592b15f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2017
---
# <a name="using-a-custom-activity"></a>使用自定义活动
派生自 <xref:System.Activities.Activity> 或其子类的活动可以组合到更大的工作流中，或以代码直接创建。 此主题说明如何使用工作流中以代码或通过设计器创建的自定义活动。  
  
> [!NOTE]
>  可以在其中定义它们，同一项目中使用自定义活动，只要自定义活动和使用它的活动都可编译 （即由生成过程生成的实例化类型加载） 如果在加载引用的活动动态 （例如使用 ActivityXAMLServices），然后应将引用的程序集放在不同的项目，或设计器生成的 XAML 需要经过手动编辑要启用此功能。  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>将自定义活动用于工作流项目  
  
1.  添加从宿主项目指向包含自定义活动的活动库项目的引用。  
  
2.  生成解决方案。  
  
3.  如要在设计器中使用自定义活动，须先在工具箱中找到自定义活动，并将该活动拖放到设计器图面上。  
  
4.  如要在代码中使用自定义活动，须添加 Using 语句，使该语句引用自定义活动项目，并将该活动的一个新实例传递给 <xref:System.Activities.WorkflowInvoker.Invoke%2A>。
