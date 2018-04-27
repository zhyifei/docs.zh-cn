### <a name="sharing-session-state-with-aspnet-stateserver-requires-all-servers-in-the-web-farm-to-use-the-same-net-framework-version"></a>与 Asp.Net StateServer 共享会话状态需要 Web 场中的所有服务器使用相同版本的 .NET Framework

|   |   |
|---|---|
|详细信息|启用 <xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=name> 会话状态时，给定 Web 场中的所有服务器必须使用相同版本的 .NET Framework 以便正确共享状态。|
|建议|请务必在同时共享状态的 Web 服务器上升级 .NET Framework 版本。|
|范围|边缘|
|版本|4.5|
|类型|运行时|
|受影响的 API|<ul><li><xref:System.Web.SessionState.SessionStateMode.StateServer?displayProperty=nameWithType></li></ul>|

