---
title: Kali Linux 与 Parrot OS：哪个渗透测试发行版最好？
date: 2024-3-21 17:14:46
tags:
- 教程
categories:
- 渗透系统
---



# Kali Linux 与 Parrot OS：哪个渗透测试发行版最好？

您是否正在尝试选择使用哪种道德黑客或注重安全的 Linux 发行版？Kali Linux 和 Parrot OS 是为此目的而设计的两个最好的 Linux 发行版。它们都是免费的，并且为安全专业人士预装了大量软件，但您知道它们之间的区别吗？

本文将研究这两个版本的 Linux、它们的易用性、它们附带的工具以及它们的性能。我们将比较他们在某些领域的优势和劣势，并突出一个人相对于另一个人的优势。

通过本文的结论，您将深入了解 Kali Linux 与 Parrot OS，并能够决定哪一个最适合您。

## 关于操作系统

Kali Linux 和 Parrot OS 都是基于 Debian 的 Linux 发行版，面向安全专业人士。Debian 是最古老、使用最广泛、最稳定的 Linux 发行版之一，其第一个版本可以追溯到 1993 年。由于 Kali 和 Parrot OS 的预期用途是针对安全专业人员，特别是黑客，因此它们有许多相同的功能。尽管如此，它们之间的关键差异可能会使它们更适合某些任务。

### 什么是 Kali Linux？

![什么是 Kali Linux](https://www.stationx.net/wp-content/uploads/2023/04/1.-What-is-Kali-Linux.png)

[Kali Linux](https://www.kali.org/get-kali/)是一个备受推崇的发行版，由[OffSec](https://www.offsec.com/)（以前称为 Offective Security）资助和开发。他们是一家网络安全公司，还提供行业标准资格，例如著名的[OffSec 认证专业人员 (OSCP)](https://www.stationx.net/ceh-vs-oscp/)、OffSec 经验丰富的渗透测试人员 (OSEP) 等等。这一血统是许多安全专业人员使用 Kali 进行渗透测试、数字取证和其他相关活动的原因之一。

Kali 的第一个版本于 2013 年发布，是已停止开发的 BackTrack 发行版的重新打包。BackTrack 包含数百个预打包工具，但因难以使用且不可靠而闻名。Kali 解决了这些弱点，成为许多专业人士使用的首选工具集，并持续定期改进和更新。 

### 什么是 Parrot 操作系统？

![什么是 Parrot 操作系统](https://www.stationx.net/wp-content/uploads/2023/04/2.-What-is-Parrot-OS.png)

[Parrot OS](https://www.parrotsec.org/download/)与 Kali 一样，是一个 Linux 发行版，它预先打包了一些可以帮助安全专业人员工作的工具。然而，它是一个社区驱动的项目，由爱好者和行业专家维护和支持。 

它们最初被称为 FrozenBox，但自 2017 年以来，目前的独立开发人员团队一直由 Lorenzo Faletra 领导。Parrot OS 专注于渗透测试、数字取证和隐私，并在发行版中预装了用于这些任务的工具和应用程序。

与 Kali 类似，BackTrack 启发了 Parrot OS，该团队希望创建一个新的发行版来继承 BackTrack 的使命。Parrot OS虽然只有一个小型的开发团队，但它持续不断地更新和改进，是安全行业中流行的Linux发行版。



**想要下载我们所有的高级备忘单吗？**

没问题！只需输入您的电子邮件地址，我们就会向您发送所有热门备忘单的 PDF 版本。

**下载 →**



## 用户体验

Kali Linux 和 Parrot OS 的主要关注点是安全专业人士，但这并不意味着它们不能看起来有吸引力、易于使用且性能良好。这两个发行版的用户体验如何相互比较？

### 卡利体验

对于任何使用过最新 Debian Linux 发行版的人来说，Kali Linux 的初始体验都会很熟悉。一切都是合乎逻辑且直观的，并且很容易找到解决办法。就连命令行也充满了色彩。

当进一步深入菜单时，大量的预装工具就会变得显而易见。如果您没有使用所有这些工具的经验，这可能会让人望而生畏，但它们按类别进行组织，以便于查找。您可以通过菜单顶部的搜索框快速找到您需要的工具。

[![卡利体验](https://www.stationx.net/wp-content/uploads/2023/04/3.-The-Kali-Experience.jpg)](https://www.stationx.net/wp-content/uploads/2023/04/3.-The-Kali-Experience.jpg)

安装 Kali 时可以选择 XfCE、GNOME 或 KDE Plasma 图形桌面环境，但大多数人会使用默认值，即 XfCE。这些选项在默认为 XfCE 的实时映像中不可用。这是一个轻量级且直观的环境，有效地消除了对旧“Kali Lite”发行版的需求。 

[![Kali软件选型](https://www.stationx.net/wp-content/uploads/2023/04/4.-Kali-Software-Selection.jpg)](https://www.stationx.net/wp-content/uploads/2023/04/4.-Kali-Software-Selection.jpg)

Kali 最近将默认 shell 从 Bash (Bourne-Again Shell) 切换为 Zsh (Z Shell)。尽管 Bash 长期以来一直是许多 Linux 发行版的默认 shell，但 Zsh 提供了更多功能和自定义功能，例如高级的基于上下文的自动完成和键盘快捷键。由于 Kali 中的许多工具都是从命令行运行的，因此 Zsh 是一个非常好用的 shell，可以使在此环境中的工作更加高效。

[![Linux 发行版](https://www.stationx.net/wp-content/uploads/2023/04/5.-Linux-Distributions.jpg)](https://www.stationx.net/wp-content/uploads/2023/04/5.-Linux-Distributions.jpg)

Kali 专注于用于渗透测试和数字取证的工具，没有预装任何办公或媒体应用程序。这些可以手动安装，但 Kali 的性质意味着不建议将其用于通用操作系统。 

您将运行的某些工具需要 root 访问权限，并且经常会导致不稳定以及需要重新安装或恢复到快照。Kali 的最新版本提高了稳定性，因为默认用户不再是 root，并且此级别的访问需要 sudo 权限升级。 

运行 Kali 的一种流行方式是作为更稳定的主机（例如 Ubuntu、Windows 或 macOS）上的虚拟机，或者作为可启动 USB 驱动器。当以这种方式使用时，操作系统的损坏不会那么灾难性，并且恢复会更快。

与大多数 Linux 发行版一样，Kali 具有很强的可定制性。可以安装不同的桌面环境、添加工具以及轻松更改配置设置。然而，正如我们所提到的，大多数人使用标准配置，因为如果操作系统因使用导致损坏的工具而遇到问题，则重建时间可以保持在最低限度。 

### Parrot 操作系统体验

对于任何使用 Linux 的家庭来说，Parrot OS 都会感到熟悉。尽管如此，从第一次使用中就可以明显看出，开发人员创建了一个非常直观、灵活且视觉上令人愉悦的工作环境。与 Kali 相比，Parrot OS 感觉敏捷且能够快速响应您的输入，即使在相对普通的硬件上也是如此。

菜单系统组织得很好，工具按逻辑分类。与 Kali 一样，种类繁多的工具可能让人眼花缭乱。幸运的是，Parrot OS 还有一个方便的搜索框，可以帮助您找到所需的内容。熟悉布局并不需要很长时间。

[![Parrot 操作系统体验](https://www.stationx.net/wp-content/uploads/2023/04/6.-The-Parrot-OS-Experience.jpg)](https://www.stationx.net/wp-content/uploads/2023/04/6.-The-Parrot-OS-Experience.jpg)

Parrot OS 使用 MATE 作为默认桌面环境，其性能和易用性与 XfCE 相当，但可定制性较差。这不是问题，因为大多数人会使用默认设置，而不关心审美变化，而是专注于使用工具。有些人可能会发现布局更直观，因为它是一个更简单的设计，但同样有效。

安装Parrot OS时无法选择桌面环境。相反，一旦新环境启动并运行，就需要安装它。一个流行的选择是 XfCE，但 MATE 并不缺少任何关键的东西，所以这完全取决于您的偏好。

Parrot OS 默认使用常见的 BASH shell。尽管不如 Kali 中使用的 Zsh shell 先进，但它仍然提供了许多出色的功能，可以提高使用效率。它具有自动完成、颜色编码和自定义功能，可帮助运行命令行工具。大多数安全专业人员都对 BASH 感到满意，但如果需要额外的功能，可以安装 Zsh。 

[![bash外壳](https://www.stationx.net/wp-content/uploads/2023/04/7.-BASH-shell.jpg)](https://www.stationx.net/wp-content/uploads/2023/04/7.-BASH-shell.jpg)

Parrot OS 预装了许多与渗透测试和数字取证相关的工具，但它还具有一些出色的隐私、匿名和加密功能。这些功能使其与 Kali 区分开来，并表明它被设计为更多地用作希望保护数据并保持隐私的安全专业人员的日常操作系统。

Parrot OS 预装了 Office 和媒体工具。虽然这些都是基础的，但如果需要的话，它确实开启了使用 Parrot OS 作为通用操作系统的可能性。此功能是 Parrot OS 受欢迎的原因之一，并且使其成为更灵活的操作系统。还提供未预装安全工具的家庭版，这可能是更适合日常使用的操作系统。

[![预装了许多工具](https://www.stationx.net/wp-content/uploads/2023/04/8.-Pre-installed-with-many-tools.jpg)](https://www.stationx.net/wp-content/uploads/2023/04/8.-Pre-installed-with-many-tools.jpg)

由于 Parrot OS 基于 Debian，因此可高度定制，使您能够创建适合您需求的环境。不过，由于Parrot OS的默认安装配置非常好，并且经常在实际环境中运行，因此大多数人没有这个需求。

| **卡利语**                                            | **鹦鹉**                                             |
| ----------------------------------------------------- | ---------------------------------------------------- |
| Xfce环境                                              | 伴侣环境                                             |
| ZSH Shell高级选项卡完成主题和插件高级定制大型活跃社区 | Bash Shell 标准制表符补全Linux 标准 Shell 兼容性熟悉 |
| 很好的表现                                            | 性能非常快                                           |
| 没有办公或媒体工具                                    | 办公和基本媒体工具                                   |
| 图形用户界面和命令行                                  | 图形用户界面和命令行                                 |
| 有些工具可能会导致系统崩溃                            | 有些工具可能会导致系统崩溃                           |
| 可定制                                                | 可定制                                               |

## 系统要求和性能

Linux 因在普通硬件上运行良好且运行方式灵活而享有盛誉。由于 Kali Linux 和 Parrot OS 基于流行的 Debian 发行版，因此它们也不例外，并且可以在各种旧平台上愉快地运行。Kali 和 Parrot OS 的性能有区别吗？请仔细阅读，找出答案。



**想要下载我们所有的高级备忘单吗？**

没问题！只需输入您的电子邮件地址，我们就会向您发送所有热门备忘单的 PDF 版本。

**下载 →**



### 运行 Kali Linux

Kali Linux 将在相当低规格的硬件上运行，仅需要 20Gb 硬盘空间、2Gb RAM 和 i3 或 AMD E1 双核处理器。一般任务在最低规格下表现良好，但如果尝试密集活动（例如密码破解），资源使用量可能会迅速增加，因此我们建议如果可能的话，使用高于最低规格的规格。

启动时间与 Linux 的其他发行版相当，整体性能足够，并且取决于可用的硬件资源。

Kali 专注于维护最新的工具和功能，并遵循滚动更新计划。这些更新可能会因其数量和频率而导致稳定性问题，因此可靠性一直是 Kali 的一个问题（尽管它们还没有致命到足以让人们远离该发行版）。 

安装 Kali Linux 的方法有很多种，包括从 ISO 完全安装到磁盘、与另一个操作系统双重启动或将[其安装为虚拟机](https://www.stationx.net/how-to-install-kali-linux-on-virtualbox/)。它还可以作为针对不同虚拟环境的预打包虚拟机映像提供。这些可以简单地插入虚拟机主机并无需任何配置即可启动。这是在现有机器上快速测试或使用 Kali 的好方法。（[在这里了解最适合 Kali Linux 的笔记本电脑](https://www.stationx.net/best-laptops-for-kali-linux/)。）

![运行 Kali Linux](https://www.stationx.net/wp-content/uploads/2023/04/9.-Running-Kali-Linux.png)

使用 ISO 映像，Kali Linux 还可以从实时 USB 设备启动。一些安全专业人员会在他们的工具包中携带实时 Kali USB 驱动器，以便他们可以在任何设备上启动并使用这些工具。如果你看过[机器人先生电视剧](https://www.stationx.net/movies-for-hackers-to-watch/)，Eliot就是这样使用直播Kali U盘的。

### 运行 Parrot 操作系统 

Parrot OS 受欢迎的原因之一是，相比之下，运行它的硬件要求非常小。它需要 1Ghz 双核 CPU，与 Kali 相同，但只有 320Gb RAM，并且没有图形加速。它可以在适度的硬件上顺利运行，但与任何操作系统一样，如果需要密集的任务，它将需要更多的资源。不过，即使在旧硬件上，整体性能也令人印象深刻。 

尽管 Parrot OS 与 Kali 有一些共同点，但它有更传统的更新时间表。Parrot OS 以其稳定性而闻名，在某种程度上，更新来自其自己的存储库，并经过兼容性和可靠性检查。但请注意，某些工具需要 root 访问权限才能运行，这可能会导致问题和损坏。在实时环境中运行 Parrot OS 是实现快速恢复的有效方法。

与 Kali 不同，Parrot OS 安全版仅作为 ISO 提供。它足够灵活，可以安装在裸机上，作为实时 USB 运行，或者作为虚拟机安装，但没有预打包的 VM 可用。这意味着在虚拟环境中运行它需要更多的准备和配置。这并不困难，但在两者之间进行选择时值得考虑额外的时间和精力。

![安全版](https://www.stationx.net/wp-content/uploads/2023/04/10.-Security-Edition.jpg)

| **卡利Linux**               | **鹦鹉操作系统**           |
| --------------------------- | -------------------------- |
| 1Ghz单核CPU（推荐2Ghz双核） | 1Ghz双核CPU                |
| 1 Gb RAM（推荐 2Gb RAM）    | 320 Mb RAM（推荐 2Gb RAM） |
| 不需要图形加速              | 不需要图形加速             |
| 20Gb硬盘空间                | 16 GB 硬盘空间             |
| 很好的表现                  | 很好的表现;很好的绩效      |
| 灵活的安装选项              | 安装选项不那么灵活         |
| 一些可靠性问题              | 稳定性和可靠性好。         |

## 工具

Kali Linux 和 Parrot OS 预配置了[600 多种针对安全专业人士的工具](https://www.stationx.net/penetration-testing-tools-for-kali-linux/)。尽管其中许多工具存在重复，但仍存在值得考虑的差异。

### Kali Linux 工具

Kali Linux 预装了 600 多个工具。这些主要针对渗透测试并分为几类。有些工具出现在多个菜单中，因为它们具有多种用途，并且可以相应地进行分类。

![Kali Linux 工具](https://www.stationx.net/wp-content/uploads/2023/04/11.-Kali-Linux-Tools.png)

### Parrot 操作系统工具

Parrot OS 预装了与 Kali 类似的工具集，但包含有助于加密、隐私和匿名的应用程序，这使其与 Kali 区分开来。菜单系统的工具组织良好且易于查找。

![Parrot 操作系统工具](https://www.stationx.net/wp-content/uploads/2023/04/12.-Parrot-OS-Tools.png)

## 支持

### 卡利支持

由于 Kali 基于 Debian，因此它使用标准的 APT 包管理器进行更新和升级。它是一个命令行工具，但易于使用并且很快就会熟悉。 

社区为 Kali 提供的支持非常出色且热情。Kali 被许多安全专业人士认为是行业标准渗透工具集，而且这种声誉多年来不断增长，用户群不断增加。

[Kali 的文档非常丰富，可以在OffSec 网站](https://www.kali.org/docs/)上找到。它通过非常深入的文章涵盖了从安装到开发的所有内容。

![卡利支持](https://www.stationx.net/wp-content/uploads/2023/04/13.-Kali-Support.jpg)



**想要下载我们所有的高级备忘单吗？**

没问题！只需输入您的电子邮件地址，我们就会向您发送所有热门备忘单的 PDF 版本。

**下载 →**



### Parrot 操作系统支持

Parrot OS 也基于 Debian，并使用 APT 作为软件包和更新管理器。它的工作方式与 Kali 相同，是一种可靠且简单的安装和更新软件包的方法。 

Parrot OS 得到了社区的良好支持；它是一个基于社区的项目，这很适合这一点。它自 2013 年推出以来，已经获得了忠实的追随者，但其支持程度无法与 Kali Linux 相比。

为 Parrot OS 提供的文档可以在[Parrot 网站](https://parrotsec.org/docs/)上找到。它表现得很好，也足够深入，很有价值。该文档涵盖了从安装到配置和云的许多主题，但不如 Kali 文档深入。

![ParrotOS 文档](https://www.stationx.net/wp-content/uploads/2023/04/14.-ParrotOS-Documentation.jpg)

| **卡利Linux**  | **鹦鹉操作系统** |
| -------------- | ---------------- |
| 优秀的社区支持 | 良好的社区支持   |
| 优秀的文档     | 良好的文档       |

## 结论

Kali Linux 和 Parrot OS 在很多方面都非常相似，但也有足够的差异，使每一种都适合不同的角色。 

Kali 是渗透测试工具集的黄金标准，提供最新、最好的工具并频繁更新。它拥有大多数任务所需的一切，并且可以轻松安装缺少的任何内容。然而，它相对消耗资源并且可能存在稳定性问题。

Parrot OS 虽然被一些人错误地认为是新来者，但它的历史和 Kali 一样悠久，并且自创建以来一直在不断发展。尽管与 Kali 相比，它在受欢迎程度上有所欠缺，但它以卓越的性能、更广泛的工具集和更直观的用户界面来弥补。它还受益于检查稳定性的适度更新，从而形成一个可能比 Kali 更可靠的稳定操作系统。

由于 Kali Linux 是行业标准安全专业人士的工具集，也是许多认证考试（例如 OSCP）所需的操作系统，因此我们强烈建议熟练使用它。

然而，Parrot OS 是一个很好的选择，它有自己出色的功能和独特的风格。它还拥有非常出色的性能和直观的环境，可以在其中学习行业工具。

![Kali Linux 与 Parrot OS 有何不同](https://www.stationx.net/wp-content/uploads/2023/04/15.-How-Is-Kali-Linux-Different-to-Parrot-OS.png)