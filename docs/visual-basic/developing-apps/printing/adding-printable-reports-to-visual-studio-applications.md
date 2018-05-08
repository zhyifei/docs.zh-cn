---
title: 将可打印的报表添加到 Visual Studio 应用程序
ms.date: 07/20/2015
helpviewer_keywords:
- printing [Visual Studio], reports
- reports [Visual Basic], printing in Visual Studio
ms.assetid: 93928405-ef41-495e-bce2-9d43d5a7080a
ms.openlocfilehash: 4a7275a665e0c3290c2b3cd55c1af0c7cf0504f2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
---
# <a name="adding-printable-reports-to-visual-studio-applications"></a>将可打印的报表添加到 Visual Studio 应用程序
Visual Studio 支持各种报表的解决方案来帮助你添加到 Visual Basic 应用程序报告的丰富数据。 你可以创建并添加使用 ReportViewer 控件、 Crystal Reports 或 SQL Server Reporting Services 报表。  
  
> [!NOTE]
>  SQL Server Reporting Services 是 SQL Server 2005，而不是 Visual Studio 的一部分。 在你的系统上未安装，除非你已安装 SQL Server 2005 reporting Services。  
  
## <a name="overview-of-microsoft-reporting-technology-in-visual-basic-applications"></a>Microsoft 报表中 Visual Basic 应用程序的技术的概述  
 从以下方法用于使用 Microsoft 报表技术应用程序中的选择：  
  
-   ReportViewer 控件的一个或多个实例添加到 Visual Basic Windows 应用程序。  
  
-   通过对报表服务器 Web 服务进行调用的以编程方式将 SQL Server Reporting Services 集成。  
  
-   使用 ReportViewer 控件和 Microsoft SQL Server 2005 Reporting Services 一起使用，为一个报表处理器为报表查看器和报表服务器使用的控件。 （请注意，是否你想要一起使用的报表服务器和 ReportViewer 控件，你必须使用 Reporting Services 的 SQL Server 2005 版本）。  
  
## <a name="using-reportviewer-controls"></a>使用 ReportViewer 控件  
 嵌入报表功能集成到 Visual Basic Windows 应用程序的最简单方法是将 ReportViewer 控件添加到你的应用程序中的窗体。 该控件将添加报表处理直接向你的应用程序的功能，并提供一个集成的报表设计器，从而使您可以生成报表使用从任何 ADO.NET 数据对象的数据。 全功能 API 提供以编程方式访问控件，并报告，以便你可以配置运行时功能。  
  
 ReportViewer 提供内置的报表处理和查看单个、 可自由地分发数据控件中的功能。 选择 ReportViewer 控件，是否你需要以下的报表功能：  
  
-   在客户端应用程序中处理的报表。 处理的报表将出现在该控件提供的视图区域。  
  
-   数据绑定到 ADO.NET 数据表。 你可以创建使用的报表<xref:System.Data.DataTable>提供给控件的实例。 此外可以直接到业务对象绑定。  
  
-   你可包括在你的应用程序的可再发行控件。  
  
-   运行时功能，例如页面导航、 打印、 搜索和导出格式。 ReportViewer 工具栏提供对这些操作的支持。  
  
 若要使用 ReportViewer 控件，可以将其从拖动**数据**的 Visual Studio 工具箱中拖动到在 Visual Basic Windows 应用程序的窗体的部分。  
  
### <a name="creating-reports-in-visual-studio-for-reportviewer-controls"></a>为 ReportViewer 控件在 Visual Studio 中创建报表  
 若要构建在 ReportViewer 中运行的报表，将添加**报表**到你的项目模板。 Visual Studio 创建的客户端报表定义文件 (.rdlc)，将文件添加到你的项目，并在 Visual Studio 工作区中打开的集成的报表设计器。  
  
 Visual Studio 报表设计器与集成**数据源**窗口。 当你将字段从**数据源**到报表中，报表设计器窗口将有关数据源的元数据复制到报表定义文件。 ReportViewer 控件使用此元数据自动生成数据绑定代码。  
  
 Visual Studio 报表设计器不包括报表预览功能。 若要预览报表、 运行应用程序和预览报表嵌入在其中。  
  
|若要将基本报表功能添加到你的应用程序|  
|---|    
|1.将 ReportViewer 控件从**数据**选项卡**工具箱**拖动到窗体。<br />2.在 **“项目”** 菜单上选择 **“添加新项”**。 在**添加新项**对话框中，选择**报表**图标，然后单击**添加**。<br />     在开发环境中，打开的报表设计器和报表 (.rdlc) 文件添加到项目。<br />3.将报表项从**工具箱**报表布局上根据需要对其进行排列。<br />4.将字段从**数据源**到报表布局中的报表项的窗口。|  
  
## <a name="using-reporting-services-in-visual-basic-applications"></a>在 Visual Basic 应用程序中使用 Reporting Services  
 Reporting Services 是一种基于服务器的报告技术所包含的 SQL Server。 Reporting Services 包括 ReportViewer 控件中找不到的其他功能。 如果你需要任何以下功能，请选择 Reporting Services:  
  
-   向外扩展部署，并且提供了改进的性能，用于复杂或长时间运行的报表和大量报表活动的服务器端报表处理。  
  
-   集成的数据和报表处理，并支持自定义报表控件和丰富的呈现输出格式。  
  
-   计划报表处理，以便你可以指定运行报表的确切时间。  
  
-   通过电子邮件或文件共享位置的基于订阅服务器的报表分发。  
  
-   特别报告，以便根据需要业务用户可以创建报表。  
  
-   将自定义的报表输出路由到收件人动态列表的数据驱动的订阅。  
  
-   数据处理、 报表传递、 自定义身份验证和报表呈现的自定义扩展。  
  
 报表服务器作为 Web 服务实现。 你的应用程序代码必须包含对 Web 服务调用，以访问报表和其他元数据。 Web 服务提供完整的报表服务器实例以编程方式访问。  
  
 由于 Reporting Services 是一项基于 Web 的报表技术，默认查看器中的 HTML 格式显示呈现的报表。 如果你不想要用作默认报表演示文稿格式的 HTML，你将需要编写一个自定义报表查看器查看你的应用程序。  
  
### <a name="creating-reports-in-visual-studio-for-reporting-services"></a>为 Reporting Services 在 Visual Studio 中创建报表  
 若要生成的报表服务器运行的报表，你创建报表定义 (.rdl) 文件在 Visual Studio 中通过 Business Intelligence Development Studio 中，包含在 SQL Server 2005。  
  
> [!NOTE]
>  你必须具有 SQL Server 2005 安装才能使用 SQL Server Reporting Services 和 Business Intelligence Development Studio。  
  
 Business Intelligence Development Studio 添加特定于 SQL Server 组件的项目模板。 若要创建的报表，可以选择从**报表服务器项目**或**报表服务器项目向导**模板。 你可以指定数据源连接和查询到各种数据源类型，包括 SQL Server、 Oracle、 Analysis Services、 XML 和 SQL Server Integration Services。 A**数据**选项卡上，**布局**选项卡上，和**预览**选项卡允许你定义数据、 创建报表布局，以及预览同一工作区中所有的报表。  
  
 为控件或报表服务器创建的报表定义可以在任一技术中重复使用。  
  
|若要创建报表服务器运行的报表|  
|---|    
|1.上**文件**菜单上，选择**新建**。<br />     **“新建项目”** 对话框随即打开。<br />2.在**项目类型**窗格中，单击**商业智能项目**。<br />3.在模板窗格中，选择**报表服务器项目**或**报表服务器项目向导**。|  
  
## <a name="using-reportviewer-controls-and-sql-server-reporting-services-together"></a>使用 ReportViewer 控件和 SQL Server Reporting Services 在一起  
 ReportViewer 控件和 SQL Server 2005 Reporting Services 可一起在同一个应用程序。  
  
-   ReportViewer 控件可提供用于在你的应用程序中显示报表查看器。  
  
-   Reporting Services 提供报表，并在远程服务器上执行所有处理。  
  
 可以配置 ReportViewer 控件以显示远程的 Reporting Services 报表服务器上的存储和处理的报表。 此类型的配置称为*远程处理模式*。 在远程处理模式下，该控件将请求存储在远程报表服务器的报表。 报表服务器执行所有报表处理、 数据处理和报表呈现。 已完成的呈现的报表是返回到控件，显示在视图区域。  
  
 在支持其他报表服务器运行的报表导出格式，具有不同的报表参数化实现，使用支持的报表服务器，并通过基于角色的授权模型上访问的数据源类型报表服务器。  
  
 若要使用远程处理模式，请指定的 URL 和服务器报表的路径配置 ReportViewer 控件时。
