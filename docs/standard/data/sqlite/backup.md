---
title: 联机备份
ms.date: 12/13/2019
description: 了解如何使用 SQLite 的联机备份功能。
ms.openlocfilehash: d857dcb69f2b2d10b034a0abf222b30c2e20bb41
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901288"
---
# <a name="online-backup"></a>联机备份

SQLite 可以在应用运行时备份数据库文件。 此功能在 `SqliteConnection`上的 <xref:Microsoft.Data.Sqlite.SqliteConnection.BackupDatabase%2A> 方法中提供。

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/BackupSample/Program.cs?name=snippet_Backup)]

目前，`BackupDatabase` 会尽快备份数据库，并阻止其他连接写入数据库。 问题[#13834](https://github.com/dotnet/efcore/issues/13834)将提供备用 API 来备份后台数据库，并允许其他连接中断备份并写入数据库。 如果你感兴趣，请提供有关该问题的反馈。
