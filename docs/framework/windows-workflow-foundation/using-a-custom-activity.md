---
title: 使用自定义活动
ms.date: 03/30/2017
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
ms.openlocfilehash: 6ca67ef7a8c4330d0182e960fc3fdcce656976a4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/22/2019
ms.locfileid: "69962227"
---
# <a name="using-a-custom-activity"></a>使用自定义活动
派生自 <xref:System.Activities.Activity> 或其子类的活动可以组合到更大的工作流中，或以代码直接创建。 此主题说明如何使用工作流中以代码或通过设计器创建的自定义活动。  
  
> [!NOTE]
> 自定义活动可以在定义它们的同一个项目中使用, 只要自定义活动和使用该活动的活动都编译 (即, 由生成进程生成的实例化类型加载) (如果已加载引用活动)动态 (例如, 使用 ActivityXAMLServices), 则引用的程序集应放置在不同的项目中, 或者需要手动编辑设计器生成的 XAML 来启用此。  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>将自定义活动用于工作流项目  
  
1. 添加从主机项目指向包含自定义活动的活动库项目的引用。  
  
2. 生成解决方案。  
  
3. 如要在设计器中使用自定义活动，须先在工具箱中找到自定义活动，并将该活动拖放到设计器图面上。  
  
4. 如要在代码中使用自定义活动，须添加 Using 语句，使该语句引用自定义活动项目，并将该活动的一个新实例传递给 <xref:System.Activities.WorkflowInvoker.Invoke%2A>。
