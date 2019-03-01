---
title: 将可打印的报表添加到 Visual Studio 应用程序
ms.date: 07/20/2015
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
ms.openlocfilehash: 65264deea3aeff1a633ea6888b3f175031b7fba5
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/01/2019
ms.locfileid: "57212009"
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a>将可打印的报表添加到 Visual Studio 应用程序
Visual Studio 支持多种报告解决方案，以帮助您向 Visual Basic 应用程序添加丰富的数据报告。 您可以创建并添加使用 ReportViewer 控件、 Crystal Reports 或 SQL Server Reporting Services 报表。  

  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a>Microsoft 报表技术在 Visual Basic 应用程序的概述  
 从以下方法用于使用 Microsoft 报表技术应用程序中的选择：  
  
-   将 ReportViewer 控件的一个或多个实例添加到 Visual Basic Windows 应用程序。  
  
-   以编程方式将 SQL Server Reporting Services 集成，从而对报表服务器 Web 服务的调用。  
  
-   使用 ReportViewer 控件和 Microsoft SQL Server 2005 Reporting Services 在一起，为报表查看器和报表服务器控件用作报表处理器。 （请注意，是否你想要一起使用的报表服务器和 ReportViewer 控件，则必须使用 SQL Server 2005 版本的 Reporting Services）。  
  
## <a name="using-reportviewer-controls"></a>使用 ReportViewer 控件  
 嵌入报表功能集成到 Visual Basic Windows 应用程序的最简单方法是将 ReportViewer 控件添加到你的应用程序中的窗体。 该控件添加报表处理直接向你的应用程序的功能，并提供了集成的报表设计器，以便您可以生成使用任何 ADO.NET 数据对象中的数据的报告。 一个全面的 API 以编程方式访问控件和报告，以便你可以配置运行时功能。  
  
 ReportViewer 提供了内置的报表处理和查看单个免费分发的数据控件中的功能。 选择 ReportViewer 控件，是否您需要以下报告功能：  
  
-   在客户端应用程序中处理的报表。 处理的报表将显示在视图区域中提供的控件。  
  
-   数据绑定到 ADO.NET 数据的表。 你可以创建报表来使用<xref:System.Data.DataTable>提供给控件的实例。 此外可以绑定到业务对象直接。  
  
-   可以在应用程序中包含的可再发行控件。  
  
-   运行时功能，例如页面导航、 打印、 搜索和导出格式。 ReportViewer 工具栏提供对这些操作的支持。  
  
 若要使用 ReportViewer 控件，可以将其从**数据**的 Visual Studio 工具箱拖到窗体在 Visual Basic Windows 应用程序中的部分。  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a>为 ReportViewer 控件在 Visual Studio 中创建报表  
 若要生成在 ReportViewer 中运行的报表，添加**报表**到你的项目模板。 Visual Studio 创建客户端报表定义文件 (.rdlc) 中，将文件添加到你的项目，并在 Visual Studio 工作区中打开集成的报表设计器。  
  
 与 Visual Studio 报表设计器集成**数据源**窗口。 当将某个字段从**数据源**到报表，报表设计器窗口将数据源有关的元数据复制到报表定义文件。 ReportViewer 控件使用此元数据自动生成数据绑定代码。  
  
 Visual Studio 报表设计器不包括报表预览功能。 若要预览报表，运行该应用程序并预览报表嵌入其中。  
  
|若要将基本报表功能添加到你的应用程序|  
|---|    
|1.中的 ReportViewer 控件拖**数据**选项卡**工具箱**拖动到窗体。<br />2.在 **“项目”** 菜单上选择 **“添加新项”**。 在中**添加新项**对话框中，选择**报表**图标，然后单击**添加**。<br />     在开发环境中，打开的报表设计器和报表 (.rdlc) 文件添加到项目。<br />3.将报表项从**工具箱**报表布局上和根据需要对其进行排列。<br />4.将字段从**数据源**报表布局中的报表项的窗口。|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a>在 Visual Basic 应用程序中使用的 Reporting Services  
 Reporting Services 是随 SQL Server 基于服务器的报告技术。 Reporting Services 包含 ReportViewer 控件中找不到的其他功能。 如果您要求任何以下功能，请选择 Reporting Services:  
  
-   横向扩展部署和服务器端报表处理提供改进的性能，对于复杂的或长时间运行的报表和大容量报表活动的。  
  
-   集成的数据和报表处理，支持自定义报表控件和丰富的呈现输出格式。  
  
-   计划报表处理，以便您可以指定运行报表的确切时间。  
  
-   通过电子邮件或文件共享位置的基于订阅服务器的报表分发。  
  
-   特别报告，以便业务用户可以根据需要创建报表。  
  
-   将自定义的报表输出路由到动态收件人列表的数据驱动订阅。  
  
-   数据处理、 报表传递、 自定义身份验证和报表呈现的自定义扩展。  
  
 报表服务器作为 Web 服务实现。 应用程序代码必须包括对 Web 服务调用，以访问报表和其他元数据。 Web 服务提供了完整以编程方式访问报表服务器实例。  
  
 Reporting Services 是基于 Web 的报告技术，因为默认查看器以 HTML 格式显示呈现的报表。 如果您不想要用作默认报表表示格式的 HTML，需要编写一个自定义报表查看器查看你的应用程序。  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a>Reporting services 在 Visual Studio 中创建报表  
 若要生成的报表服务器上运行的报表，报表定义 (.rdl) 文件中创建 Visual Studio 中通过 Business Intelligence Development Studio 中，这是 SQL Server 2005。  
  
 Business Intelligence Development Studio 添加特定于 SQL Server 组件的项目模板。 若要创建的报表，可以选择从**报表服务器项目**或**报表服务器项目向导**模板。 您可以指定数据源连接和对各种数据源类型，包括 SQL Server、 Oracle、 Analysis Services、 XML 和 SQL Server Integration Services 的查询。 一个**数据**选项卡上，**布局**选项卡上，并且**预览**选项卡可以定义数据、 创建报表布局并预览相同的工作区中的所有报表。  
  
 为控件或报表服务器生成的报表定义可以在其中一种技术中重用。  
  
|若要创建报表服务器运行的报表|  
|---|    
|1.上**文件**菜单中，选择**新建**。<br />     **“新建项目”** 对话框随即打开。<br />2.在中**项目类型**窗格中，单击**商业智能项目**。<br />3.在模板窗格中选择**报表服务器项目**或**报表服务器项目向导**。|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a>ReportViewer 控件和 SQL Server Reporting Services 一起使用  
 ReportViewer 控件和 SQL Server 2005 Reporting Services 可同时在同一应用程序。  
  
-   ReportViewer 控件提供了用于在应用程序中显示报表查看器。  
  
-   Reporting Services 提供了报表，并在远程服务器上执行所有处理。  
  
 可以配置 ReportViewer 控件以显示远程 Reporting Services 报表服务器上存储和处理的报表。 调用此类型的配置*远程处理模式*。 在远程处理模式下，该控件将请求存储在远程报表服务器的报表。 报表服务器执行所有报表处理、 数据处理和呈现报表。 完成后，将呈现的报表是返回到该控件并显示在视图区域中。  
  
 支持其他报表服务器运行的报表导出格式，具有不同的报表参数化实现，使用支持的报表服务器，并通过基于角色的授权模型上进行访问的数据源类型报表服务器。  
  
 若要使用远程处理模式，请指定 URL 和服务器报表的路径配置 ReportViewer 控件时。
