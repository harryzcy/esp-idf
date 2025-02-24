ESP-IDF 版本简介
================

:link_to_translation:`en:[English]`

ESP-IDF 的 GitHub 仓库时常更新，特别是用于开发新特性的 master 分支。

如有量产需求，请使用稳定版本。


发布版本
---------

通过以下链接，可以访问各个版本的配套文档：

* 最新稳定版 ESP-IDF：https://docs.espressif.com/projects/esp-idf/zh_CN/stable/

* 最新版 ESP-IDF（即 master 分支）：https://docs.espressif.com/projects/esp-idf/zh_CN/latest/

ESP-IDF 在 GitHub 平台上的完整发布历史请见 `发布说明页面`_。该页面支持查看各个版本的发布说明、配套文档及相应获取方式。


.. only:: html

    此外，也可以直接前往文档页面，查看不同 ESP-IDF 版本的配套文档，具体可点击页面左上角中版本的下拉菜单（在目标下拉菜单和搜索栏之间），实现在不同版本间切换。

    .. image:: /../_static/choose_version.png

    旧版本的文档也仍然可用：

    .. raw:: html
        :file: ../_static/version_table.html




我该选择哪个版本？
----------------------

- 如有量产需求，请使用 `最新稳定版本`_ 。稳定版本已通过人工测试，后续更新仅修复 bug，主要特性不受影响（更多详情，请见 :ref:`versioning-scheme` ）。请访问 `发布说明页面`_ 界面查看每一个稳定发布版本。另外，为确保使用的 ESP-IDF 版本与需生产的芯片版本兼容，可参考 `ESP-IDF 版本与乐鑫芯片版本兼容性 <https://github.com/espressif/esp-idf/blob/master/COMPATIBILITY_CN.md>`_。

- 如需尝试/测试 ESP-IDF 的最新特性，请使用 `最新版本（在 master 分支上） <https://docs.espressif.com/projects/esp-idf/zh_CN/latest/>`_。最新版本包含 ESP-IDF 的所有最新特性，已通过自动化测试，但尚未全部完成人工测试（因此存在一定风险）。

- 如需使用稳定版本中没有的新特性，但同时又不希望受到 master 分支更新的影响，可以按照需求选择一个最适合的稳定版本，将其 :ref:`更新至一个预发布版本` 或 :ref:`更新至一个发布分支`。

- 如需使用其他基于 ESP-IDF 的项目，请先查看该项目的文档，以确定其兼容的 ESP-IDF 版本。

有关如何更新 ESP-IDF 本地副本的内容，请参考 :ref:`updating` 章节。

.. _versioning-scheme:

版本管理
-----------------

ESP-IDF 采用了 `语义版本管理方法 <https://semver.org/>`_，你可以从字面含义理解每个版本的差异。其中

- 主要版本（例 ``v3.0``）代表有重大更新，包括增加新特性、改变现有特性及移除已弃用的特性。

    升级至一个新的主要版本（例 ``v2.1`` 升级至 ``v3.0``）意味着你可能需要更新工程代码，并重新测试工程，具体可参考 `发布说明页面`_ 的重大变更 (Breaking Change) 部分。

- 次要版本（例 ``v3.1``）代表有新增特性和 bug 修复，但现有特性不受影响，公开 API 的使用也不受影响。

    升级至一个新的次要版本（例 ``v3.0`` 升级至 ``v3.1``）意味着你可能不需要更新工程代码，但需重新测试工程，特别是 `发布说明页面`_ 中专门提到的部分。

- Bugfix 版本（例 ``v3.0.1``）仅修复 bug，并不增加任何新特性。

    升级至一个新的 Bugfix 版本（例 ``v3.0`` 升级至 ``v3.0.1``）意味着你不需要更新工程代码，仅需测试与本次发布修复 bug（列表见 `发布说明页面`_）直接相关的特性。

支持期限
---------------

ESP-IDF 的每个主要版本和次要版本都有相应的支持期限。支持期限满后，版本停止更新维护，将不再提供支持。

`支持期限政策`_ 对此有具体描述，并介绍了每个版本的支持期限是如何界定的。

`发布说明页面`_ 界面上的每一个发布版本都提供了该版本的支持期限信息。

一般而言：

- 如果你刚开始一个新项目，建议使用最新稳定版本。
- 如果你有 GitHub 账号，请点击 `发布说明页面`_ 界面右上角的 "Watch" 按键，并选中 "Releases only" 选项。GitHub 将会在新版本发布的时候发送通知。当你所使用的版本有 Bugfix 版本发布时，请做好升级至该 Bugfix 版本的规划。
- 如可能，请定期（如每年一次）将项目的 IDF 版本升级至一个新的主要版本或次要版本。对于次要版本更新，更新过程应该比较简单，但对于主要版本更新，可能需要细致查看发布说明并做对应的更新规划。
- 请确保你所使用的版本停止更新维护前，已做好升级至新版本的规划。

ESP-IDF 的每个主要版本和次要版本（V4.1、V4.2 等）的支持期限为 30 个月，从最初的稳定版发布日算起。

在支持期限内意味着 ESP-IDF 团队将继续在 GitHub 的发布分支上进行 bug 修复、安全修复等，并根据需要定期发布新的 Bugfix 版本。

支持期限分为“服务期”和“维护期”：

.. list-table::
   :header-rows: 1
   :widths: 25 25 55

   * - 周期
     - 时长
     - 是否推荐新工程使用
   * - 服务期
     - 12 个月
     - 是
   * - 维护期
     - 18 个月
     - 否

在服务期内，Bugfix 版本的发布更为频繁。某些情况下，在服务期内会增加新特性，这些特性主要是为了满足新产品特定监管要求或标准，并且回归风险非常低。

在维护期内，该版本仍受支持，但只会对严重性较高的问题或安全问题进行 bug 修复。

当开始一个新项目时，建议使用在服务期内的版本。

鼓励用户在所用版本支持期限结束之前，将所有的工程升级到最新的 ESP-IDF 版本。在版本支持期限满后，我们将不再继续进行 bug 修复。

支持期限不包括预发布版本（betas、预览版、 `-rc` 和 `-dev` 版等），有时会将某个特性在发布版中标记为“预览版”，这意味着该特性也不在支持期限内。

关于 `不同版本的 ESP-IDF <https://docs.espressif.com/projects/esp-idf/en/latest/versions.html>`_ （主要版本、次要版本、Bugfix 版本等）的更多信息，请参考 ESP-IDF 编程指南。


.. image:: https://dl.espressif.com/dl/esp-idf/support-periods.svg


查看当前版本
----------------------------

查看 ESP-IDF 本地副本的版本，请使用 idf.py 命令::

    idf.py --version

此外，由于 ESP-IDF 的版本也已编译至固件中，因此你也可以使用宏 ``IDF_VER`` 查看 ESP-IDF 的版本（以字符串的格式）。ESP-IDF 默认引导加载程序会在设备启动时打印 ESP-IDF 的版本。请注意，在 GitHub 仓库中的代码更新时，代码中的版本信息仅会在源代码重新编译或在清除编译时才会更新，因此打印出来的版本可能并不是最新的。

如果编写的代码需要支持多个 ESP-IDF 版本，可以在编译时使用 :ref:`compile-time macros<idf-version-h>` 检查版本。

几个 ESP-IDF 版本的例子：

=============================== ===================================================================================================
版本字符串                        含义
=============================== ===================================================================================================
``v3.2-dev-306-gbeb3611ca``     | master 分支上的预发布版本。
                                |     - ``v3.2-dev``：为 v3.2 进行的开发。
                                |     - ``306``：v3.2 开发启动后的 commit 数量。
                                |     - ``beb3611ca``：commit 标识符。
``v3.0.2``                        稳定版本，标签为 ``v3.0.2``。
``v3.1-beta1-75-g346d6b0ea``    | v3.1 的 beta 测试版本（可参考 :ref:`更新至一个发布分支`）。
                                |     - ``v3.1-beta1`` - 预发布标签。
                                |     - ``75``：添加预发布 beta 标签后的 commit 数量。
                                |     - ``346d6b0ea``：commit 标识符。

``v3.0.1-dirty``                | 稳定版本，标签为 ``v3.0.1``。
                                |     - ``dirty`` 代表 ESP-IDF 的本地副本有修改。
=============================== ===================================================================================================

Git 工作流
------------

乐鑫 ESP-IDF 团队的 (Git) 开发工作流程如下：

- 新的改动总是在 master 分支（最新版本）上进行。master 分支上的 ESP-IDF 版本总带有 ``-dev`` 标签，表示“正在开发中”，例 ``v3.1-dev``。
- 这些改动将首先在乐鑫的内部 Git 仓库进行代码审阅与测试，而后在自动化测试完成后推至 GitHub。
- 新版本一旦完成特性开发（在 ``master`` 分支上进行）并达到进入 beta 测试的标准，则将该版本切换至一个新分支（例  ``release/v3.1``）。此外，该分支还打上预发布标签（例 ``v3.1-beta1``）。你可以在 GitHub 平台上查看 ESP-IDF 的完整 `分支列表`_ 和 `标签列表`_。Beta 预发布版本可能仍存在大量“已知问题”(Known Issue)。
- 随着对 beta 版本的不断测试，bug 修复将同时增加至该发布分支和 ``master`` 分支。而且，``master`` 分支可能也已经开始为下个版本开发新特性了。
- 当测试快结束时，该发布分支上将增加一个 rc 标签，代表候选发布 (Release Candidate) ，例 ``v3.1-rc1``。此时，该分支仍属于预发布版本。
- 如果一直未发现或报告重大 bug，则该预发布版本将最终增加“主要版本”（例 ``v4.0``）或“次要版本”标记（例 ``v3.1``），成为正式发布版本，并体现在 `发布说明页面`_ 。
- 后续，发布版本中发现的 bug 都将在该发布分支上进行修复。
- 发布分支上会定期进行 bug 修复，人工测试完成后，该分支将增加一个 Bugfix 版本标签（例 ``v3.1.1``），并体现在 `发布说明页面`_ 。


.. _updating:

更新 ESP-IDF
----------------

请根据实际情况，对 ESP-IDF 进行更新。

- 如有量产用途，建议参考 :ref:`更新至一个稳定发布版本`。
- 如需测试/研发/尝试最新特性，建议参考 :ref:`更新至 master 分支` 。
- 两者折衷建议参考 :ref:`更新至一个发布分支`。

.. note::

    在参考本指南时，请首先获得 ESP-IDF 的本地副本，具体步骤请参考 :doc:`入门指南 </get-started/index>` 中的介绍。


.. _`更新至一个稳定发布版本`:

更新至一个稳定发布版本
^^^^^^^^^^^^^^^^^^^^^^^^^^

对于量产用户，推荐更新至一个新的 ESP-IDF 发布版本，请参考以下步骤：

- 请定期查看 `发布说明页面`_ ，了解最新发布情况。
- 如有新发布的 Bugfix 版本（例 ``v3.0.1`` 或 ``v3.0.2``）时，请将新的 Bugfix 版本更新至你的 ESP-IDF 目录。
- 在 Linux 或 macOS 系统中，请运行如下命令将分支更新至 vX.Y.Z：

.. code-block:: bash

    cd $IDF_PATH
    git fetch
    git checkout vX.Y.Z
    git submodule update --init --recursive

- 在 Windows 系统中，需要将 ``cd $IDF_PATH`` 替换为 ``cd %IDF_PATH%``。
- 在主要版本或次要版本新发布时，请查看发布说明中的具体描述，并决定是否升级版本。具体命令与上方描述一致。

.. note::

    如果你在安装 ESP-IDF 时使用的是 zip 文件包，而非通过 Git 命令，则将无法使用 Git 命令进行版本升级，此属正常情况。这种情况下，请重新下载最新 zip 文件包，并替换掉之前 ``IDF_PATH`` 下的全部内容。


.. _`更新至一个预发布版本`:

更新至一个预发布版本
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

你也可以将你的本地副本切换（命令 ``git checkout``）至一个预发布版本或 rc 版本，具体方法请参考 :ref:`更新至一个稳定发布版本` 中的描述。

预发布版本通常不体现在 `发布说明页面`_。更多详情，请查看完整 `标签列表`_。使用预发布版本的注意事项，请参考 :ref:`更新至一个发布分支` 中的描述。

.. _`更新至 master 分支`:

更新至 master 分支
^^^^^^^^^^^^^^^^^^^^^^^^^

.. note::

    ESP-IDF 中 master 分支上的代码会时时更新，因此使用 master 分支相当在“流血的边缘试探”，存在一定风险。

如需使用 ESP-IDF 的 master 分支，请参考以下步骤：

- 在 Linux 或 macOS 系统中，使用如下命令在本地切换至 master 分支：

.. code-block:: bash

    cd $IDF_PATH
    git checkout master
    git pull
    git submodule update --init --recursive

- 在 Windows 系统中，需要将 ``cd $IDF_PATH`` 替换为 ``cd %IDF_PATH%``。
- 此外，你还应在后续工作中不时使用 ``git pull`` 命令，将远端 master 上的更新同步到本地。注意，在更新 master 分支后，你可能需要更改工程代码，也可能遇到新的 bug。
- 如需从 master 分支切换至一个发布分支或稳定版本，请使用 ``git checkout`` 命令。

.. important::

    强烈建议定期使用 ``git pull`` 和 ``git submodule update --init --recursive`` 命令，确保本地副本得到及时更新。旧的 master 分支相当于一个“快照”，可能存在未记录的问题，且无法获得支持。对于半稳定版本，请参考 :ref:`更新至一个发布分支`。

.. _`更新至一个发布分支`:

更新至一个发布分支
^^^^^^^^^^^^^^^^^^^^^^^^^^^^

从稳定性来说，使用“发布分支”相当于在使用 master 分支和稳定版本之间进行折衷，包含一些 master 分支上的新特性，但也同时保证可通过 beta 测试且基本完成了 bug 修复。

更多详情，请前往 GitHub 查看完整 `标签列表`_。

例如，在 Linux 或 macOS 系统中，可以运行以下命令更新至 ESP-IDF v3.1，随时关注该分支上的 Bugfix 版本发布（如 ``v3.1.1`` 等）：

.. code-block:: bash

    cd $IDF_PATH
    git fetch
    git checkout release/v3.1
    git pull
    git submodule update --init --recursive

在 Windows 系统中，需要将 ``cd $IDF_PATH`` 替换为 ``cd %IDF_PATH%``。

每次在该分支上使用 ``git pull`` 时，都相当于把最新的 Bugfix 版本发布更新至你的本地副本中。

.. note::

    发布分支并不会有专门的配套文档，建议使用与本分支最接近版本的文档。

.. _`发布说明页面`: https://github.com/espressif/esp-idf/releases
.. _`分支列表`: https://github.com/espressif/esp-idf/branches
.. _`标签列表`: https://github.com/espressif/esp-idf/tags
.. _`最新稳定版本`: https://docs.espressif.com/projects/esp-idf/zh_CN/stable/
.. _`支持期限政策`: https://github.com/espressif/esp-idf/blob/master/SUPPORT_POLICY_CN.md
