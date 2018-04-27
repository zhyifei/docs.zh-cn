### <a name="profiling-aspnet-mvc4-apps-can-lead-to-fatal-execution-engine-error"></a>分析 ASP.Net MVC4 应用可能导致严重的执行引擎错误

|   |   |
|---|---|
|详细信息|使用 NGEN /Profile 程序集的探查器可能会在启动时使已配置的 ASP.NET MVC4 应用程序出故障，引发“严重的执行引擎异常”|
|建议|此问题已在 .NET Framework 4.5.2 中解决。 或者，探查器可通过在其事件掩码中指定 <code>COR_PRF_DISABLE_ALL_NGEN_IMAGES</code> 来避免此问题。|
|范围|边缘|
|版本|4.5|
|类型|运行时|

