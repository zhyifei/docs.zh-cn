---
title: 基础结构即代码
description: 构建适用于 Azure 的云本机 .NET 应用 |基础结构即代码
ms.date: 06/30/2019
ms.openlocfilehash: 3957da68ac28774f899f49fb181a29c2435902f8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841779"
---
# <a name="infrastructure-as-code"></a>基础结构即代码

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

云本机应用程序倾向于使用各种极好的平台即服务（PaaS）组件。 在 Azure 等云平台上，这些组件可能包括存储、服务总线和 SignalR 服务等。 随着应用程序变得更加复杂，使用的这些服务的数量可能会增长。 正如持续交付如何破坏部署到环境的传统模型一样，更改的快速进度还打破了集中式 IT 组管理环境的模型。

构建环境既可以也可以自动进行。 很多人都可以轻松地了解各种工具。

## <a name="azure-resource-manager-templates"></a>Azure 资源管理器模板

Azure 资源管理器模板是一种基于 JSON 的语言，用于定义 Azure 中的各种资源。 基本架构如图11-10 所示。

```json
{
  "$schema": "https://schema.management.azure.com/schemas/2015-01-01/deploymentTemplate.json#",
  "contentVersion": "",
  "apiProfile": "",
  "parameters": {  },
  "variables": {  },
  "functions": [  ],
  "resources": [  ],
  "outputs": {  }
}
```

**图 11-10** -资源管理器模板的架构

在此模板中，可能会在资源部分中定义一个存储容器，如下所示：

```json
"resources": [
    {
      "type": "Microsoft.Storage/storageAccounts",
      "name": "[variables('storageAccountName')]",
      "location": "[parameters('location')]",
      "apiVersion": "2018-07-01",
      "sku": {
        "name": "[parameters('storageAccountType')]"
      },
      "kind": "StorageV2",
      "properties": {}
    }
  ],
```

**图 11-11** -资源管理器模板中定义的存储帐户的示例

模板可以参数化，以便可以将一个模板用于不同的设置来定义开发、QA 和生产环境。 如果迁移到与较低环境不同的环境，这有助于消除意外情况。 模板中定义的资源通常都是在 Azure 上的单个资源组中创建的（可以在单个资源管理器模板中定义多个资源组，但这种情况并不常见）。 这样，只需删除整个资源组即可轻松删除环境。 成本分析还可以在资源组级别运行，从而可以快速评估每个环境的成本。

GitHub 上的[Azure 快速入门模板](https://github.com/Azure/azure-quickstart-templates)项目中定义了多个示例模板，这些模板将在启动新模板或将其添加到现有模板时提供一段时间。

可以通过多种方式运行资源管理器模板。 最简单的方法是将它们粘贴到 Azure 门户中。 对于实验部署，此方法非常简单。 它们还可以作为 Azure DevOps 中的生成或发布过程的一部分运行。 有一些任务将利用连接到 Azure 运行模板。 对资源管理器模板的更改以增量方式应用，这意味着，若要添加新资源，只需将其添加到模板。 工具将处理当前资源组与模板中定义的所需资源组的比较。 然后，将创建或更改资源，使其与模板中定义的内容相匹配。  

## <a name="terraform"></a>Terraform

资源管理器模板的一个明显缺点是它们特定于 Azure 云。 创建包含来自多个云的资源的应用程序是很罕见的，但是，如果企业依赖于工作正常运行时间，则支持多个云的成本可能值得。 如果有一种可跨每个云使用的模板化语言，则它还会使开发人员的技能更易于移植。

有多种技术可实现这一点。 该空间中最成熟的产品称为[Terraform](https://www.terraform.io/)。 Terraform 支持每个主要的云播放器，如 Azure、Google Cloud Platform、AWS 和 AliCloud，并且还支持数十个次要玩家，如 Heroku 和 DigitalOcean。 它使用的简要 YAML 略有不同，而不是使用 JSON 作为模板定义语言。

图11-12 中显示了一个示例 Terraform 文件，该文件与以前的资源管理器模板相同（图11-11）：

```terraform
provider "azurerm" {
  version = "=1.28.0"
}

resource "azurerm_resource_group" "test" {
  name     = "production"
  location = "West US"
}

resource "azurerm_storage_account" "testsa" {
  name                     = "${var.storageAccountName}"
  resource_group_name      = "${azurerm_resource_group.testrg.name}"
  location                 = "${var.region}"
  account_tier             = "${var.tier}"
  account_replication_type = "${var.replicationType}"

}
```

**图 11-12** -资源管理器模板的示例

当由于模板中的错误而无法部署资源时，Terraform 提供了合理的错误消息。 这是一个区域，其中资源管理器模板有一些正在进行的挑战。 还有一个非常方便的验证任务，可在生成阶段使用该任务来提前捕获模板错误。

与资源管理器模板一样，可以使用命令行工具来部署 Terraform 模板。 Azure Pipelines 中还提供了社区创建的任务，可以验证和应用 Terraform 模板。

如果 "Terraform" 或 "资源管理器" 模板将有趣的值（如连接字符串）输出到新创建的数据库，则可以在生成管道中捕获这些值，并在后续任务中使用它们。

>[!div class="step-by-step"]
>[上一页](devops.md)
>[下一页](application-bundles.md)
