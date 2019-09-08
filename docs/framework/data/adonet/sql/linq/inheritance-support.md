---
title: 层次结构支持
ms.date: 03/30/2017
ms.assetid: 19bb2794-b4e7-402e-8307-1d1517381a08
ms.openlocfilehash: 034aa6e75ca304d98aa4d3e1f3023c1a6940b73c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781565"
---
# <a name="inheritance-support"></a>层次结构支持
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]支持*单表映射*。 换言之，整个继承层次结构存储在单个数据库表中。 该表包含整个层次结构的所有可能数据列的平展联合。 （联合是将两个表组合成一个表的结果，组合后的表包含任一原始表中存在的行。）每行中不适用于该行所表示的实例类型的列为 null。  
  
 单表映射策略是最简单的继承表示形式，为许多不同类别的查询提供了良好的性能特征。  
  
 若要在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中实现这种映射，必须在继承层次结构的根类中指定属性 (Attribute) 和属性 (Attribute) 的属性 (Property)。 有关详细信息，请参阅[如何：映射继承层次](how-to-map-inheritance-hierarchies.md)结构。  
  
 使用 Visual Studio 的开发人员还可以使用对象关系设计器来映射继承层次结构。  
  
## <a name="see-also"></a>请参阅

- [背景信息](background-information.md)
