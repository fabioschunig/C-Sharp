# C#

## Description
C# studies and code snippets

## Versão

### Descobrir a versão do .NET Framework instalada

Execute no PowerShell:

``` Shell
Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP\v4\Full\' | Get-ItemPropertyValue -Name Version
```

Esse comando lerá o registro do Windows e retornará a versão atual (por exemplo, 4.8.09032).

Mais completa:

``` Shell
Get-ChildItem 'HKLM:\SOFTWARE\Microsoft\NET Framework Setup\NDP' -Recurse | Get-ItemProperty -Name Version,Release -EA 0 | Select-Object @{N='.NET Version';E={$_.Version}}, Release, PSChildName
```

### Versões mais modernas

Com versões mais modernas (como .NET Core ou .NET 5/6/7/8), a verificação é feita de maneira diferente.

Execute no prompt de comando:

``` Shell
dotnet --version
```

Para ver os detalhes completos do seu ambiente, utilize:

``` Shell
dotnet --info
```
