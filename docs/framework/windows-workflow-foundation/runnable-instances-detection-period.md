---
title: 可运行实例的检测周期
ms.date: 03/30/2017
ms.assetid: 4ea5c787-b638-47fd-bfc8-ede8c2898ce6
ms.openlocfilehash: 7b12353c3bd18367618825d22d020391b14ec3f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33513232"
---
# <a name="runnable-instances-detection-period"></a>可运行实例的检测周期
SQL 工作流实例存储运行一个内部任务，该任务将定期唤醒并检测持久性数据库中是否有可运行或可激活的实例。 **可运行实例的检测周期**SQL 工作流实例存储的属性指定的时间段后，SQL 工作流实例存储将运行一个检测任务，以检测任何可运行或可激活的工作流在上一检测周期后持久性数据库中的实例。  
  
 为此属性设置一个较短的间隔可减少与工作流实例相关联的计时器到期与发出事件信号并在随后加载实例之间的时间。 但是，这同时也会增大主机上的处理负载，在很少采用持久性计时器和/或很少发生主机故障的情况下，您可能不希望采用此类设置。 该属性的类型为 TimeSpan，其值遵循以下格式：hh:mm:ss。 该属性的最小值为 00:00:01， 默认值为 00:00:05。  
  
 有关详细信息检测和激活可运行且可激活的工作流实例，请参阅[实例激活](../../../docs/framework/windows-workflow-foundation/instance-activation.md)。
