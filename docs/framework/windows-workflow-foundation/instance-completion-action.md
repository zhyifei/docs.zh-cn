---
title: 实例完成操作
ms.date: 03/30/2017
ms.assetid: 90cc99d2-9fef-42fd-bcbf-a56917993721
ms.openlocfilehash: d68f41a586e44f96c9ca26cf8a142a2782adaa36
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "64662979"
---
# <a name="instance-completion-action"></a>实例完成操作
**实例完成操作**SQL 工作流实例存储的属性，可以指定是否删除数据和元数据的工作流实例从持久性数据库实例完成之后也会。 此属性允许的值为**DeleteAll**并**DeleteNothing**。 以下列表对这两个选项进行了说明：  
  
- **DeleteAll （默认值）。** 如果该属性的值设置为 DeleteAll，则在工作流实例完成之后会将从持久性数据库中删除该实例的数据和元数据。  
  
- **DeleteNothing。** 如果该属性的值设置为 DeleteNothing，则即使在工作流实例完成之后也会将该实例的数据和元数据保留在持久性数据库中。  
  
    > [!CAUTION]
    >  实例完成之后继续保留实例状态信息会导致持久性数据库增大。 随着数据库的增大，持久性子系统执行数据库操作所花费的时间会越来越长，因此需要定期从持久性数据库中清除实例状态信息，以使服务在满足您的性能需求的级别执行。
