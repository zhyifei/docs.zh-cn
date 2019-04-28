---
title: 使用自定义活动
ms.date: 03/30/2017
ms.assetid: 8f356419-681a-4175-ae93-878eee970249
ms.openlocfilehash: 47ddd42168445aa23eaaded6fd19ffe4698e4117
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "61669571"
---
# <a name="using-a-custom-activity"></a>使用自定义活动
派生自 <xref:System.Activities.Activity> 或其子类的活动可以组合到更大的工作流中，或以代码直接创建。 此主题说明如何使用工作流中以代码或通过设计器创建的自定义活动。  
  
> [!NOTE]
>  可以在其中定义它们，在同一项目中使用自定义活动，只要自定义活动和活动可使用它进行编译 （即由实例化类型生成的生成过程加载） 如果加载引用的活动动态 （例如使用 ActivityXAMLServices），然后应将引用的程序集放在不同的项目，或设计器生成 XAML 需要经过手动编辑，若要启用此功能。  
  
#### <a name="using-a-custom-activity-to-a-workflow-project"></a>将自定义活动用于工作流项目  
  
1. 添加从主机项目指向包含自定义活动的活动库项目的引用。  
  
2. 生成解决方案。  
  
3. 如要在设计器中使用自定义活动，须先在工具箱中找到自定义活动，并将该活动拖放到设计器图面上。  
  
4. 如要在代码中使用自定义活动，须添加 Using 语句，使该语句引用自定义活动项目，并将该活动的一个新实例传递给 <xref:System.Activities.WorkflowInvoker.Invoke%2A>。
