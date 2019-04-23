---
ms.openlocfilehash: ffafb0c9e3982dd168f907d32a8f59f96e6040d0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2019
ms.locfileid: "59234621"
---
### <a name="building-an-entity-framework-edmx-with-visual-studio-2013-can-fail-with-error-msb4062-if-using-the-entitydeploysplit-or-entityclean-tasks"></a>如果使用 EntityDeploySplit 或 EntityClean 任务，使用 Visual Studio 2013 生成 Entity Framework edmx 会失败，错误编码为 MSB4062

|   |   |
|---|---|
|详细信息|MSBuild 12.0 工具（包括在 Visual Studio 2013 中）更改了 MSBuild 文件位置，使得旧 Entity Framework 目标文件变为无效文件。 结果是 <code>EntityDeploySplit</code> 和 <code>EntityClean</code> 任务失败，因为它们无法找到 <code>Microsoft.Data.Entity.Build.Tasks.dll</code>。 请注意，此中断是由于工具集 (MSBuild/VS) 更改而引起的，并不是因为 .NET Framework 更改。 它仅在升级开发人员工具时才会发生，仅升级 .NET Framework 不会发生。|
|建议|从 .NET Framework 4.6 开始，Entity Framework 目标文件已修复，可与新 MSBuild 布局一起使用。 升级到该版本的 Framework 将解决此问题。 或者，可使用[此解决方法](https://stackoverflow.com/a/24249247/131944)直接修补目标文件。|
|范围|主要|
|Version|4.5.1|
|类型|重定目标|
