---
title: dotnet remove reference 命令 - .NET Core CLI
description: dotnet remove reference 命令可便于删除项目间引用。
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 0b7fb2788ccc04b54bf02f0387141d501612c16d
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-remove-reference"></a>dotnet remove reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>name

`dotnet remove reference` - 删除“项目到项目”引用。

## <a name="synopsis"></a>摘要

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a>描述

使用 `dotnet remove reference` 命令可方便地从项目删除项目引用。

## <a name="arguments"></a>自变量

`PROJECT`

目标项目文件。 如果未指定，此命令会搜索当前目录来获取一个项目文件。

`PROJECT_REFERENCES`

要删除的项目到项目 (P2P) 引用。 可指定一个或多个项目。 基于 Unix/Linux 的终端支持 [Glob 模式](https://en.wikipedia.org/wiki/Glob_(programming))。

## <a name="options"></a>选项

`-h|--help`

打印出有关命令的简短帮助。

`-f|--framework <FRAMEWORK>`

仅在以特定[框架](../../standard/frameworks.md)为目标时删除引用。

## <a name="examples"></a>示例

从指定项目删除项目引用：

`dotnet remove app/app.csproj reference lib/lib.csproj`

从当前目录中的项目删除多个项目引用：

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

使用 Unix/Linux 的 glob 模式删除多个项目引用：

`dotnet remove app/app.csproj reference **/*.csproj`
