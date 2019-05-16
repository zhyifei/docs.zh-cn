---
title: 如何：添加数据服务引用 （WCF 数据服务）
ms.date: 08/24/2018
helpviewer_keywords:
- WCF Data Services, configuring
ms.assetid: 62c6f318-3ee1-433a-b7a3-efa234c3034c
ms.openlocfilehash: 8bf623ec74c3bd165f63f60e883bfcb532d6900b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633961"
---
# <a name="how-to-add-a-data-service-reference-wcf-data-services"></a>如何：添加数据服务引用 (WCF Data Services)

可以使用**添加服务引用**对话框在 Visual Studio 中添加对 WCF 数据服务的引用。 这使您可以更轻松地在使用 Visual Studio 开发的客户端应用程序中访问数据服务。 完成此过程后，会基于从数据服务获取的元数据生成数据类。 有关详细信息，请参阅[生成数据服务客户端库](../../../../docs/framework/data/wcf/generating-the-data-service-client-library-wcf-data-services.md)。

## <a name="add-a-data-service-reference"></a>添加数据服务引用

1. （可选）如果数据服务不是解决方案的一部分，且未运行，请启动数据服务，并记下数据服务的 URI。

2. 在 Visual Studio 中，在**解决方案资源管理器**，右键单击客户端项目，然后选择**添加** > **服务引用**。

3. 如果数据服务当前解决方案的一部分，请单击**发现**。

     或

     在中**地址**文本框中，键入数据服务的基 URL 如`http://localhost:1234/Northwind.svc`，然后单击**转**。

4. 选择 **确定**。

     包含可以访问并与数据服务资源进行交互的数据类的新代码文件添加到项目。

## <a name="see-also"></a>请参阅

- [快速入门](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md)
