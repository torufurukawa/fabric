======
Fabric
======

..
  Status
  ======

状態
====

..
  This documentation is for Fabric's currently in-development version, which will
  eventually become Fabric 1.0. As such, it is subject to change and will not be
  set in stone until the beta release at the earliest. Additionally, the code and
  documentation may at times be out of sync, so please keep this in mind.

この文書は Fabric 1.0 用に執筆途中です。そのため、早くともベータ版が出
るまでは記述されている内容に、まだ変更があり、確定していない事項が含ま
れます。また、コードも実際の Fabric の仕様を反映していないことがあるの
で、ご注意ください。

..
  About
  =====

概要
====

.. include:: ../README_jp


..
  Installation
  ============

インストール
============

..
  Stable releases of Fabric are best installed via ``easy_install`` or ``pip``;
  or you may download TGZ or ZIP source archives from a couple of official
  locations. Detailed instructions and links may be found on the
  :doc:`installation` page.

``easy_install`` や ``pip`` を使用すれば、適切な安定リリース版の
Fabric がインストールされます; または、オフィシャルサイトから、TGZ や
ZIP のソースアーカイブをダウンロードすることも可能です。詳細な方法やリ
ンクは :doc:`installation` ページを参照して下さい。

..
  We recommend using the latest stable version of Fabric; releases are made often
  to prevent any large gaps in functionality between the latest stable release
  and the development version.

最新安定版の Fabric を使用することをお薦めします; 最新安定版と開発版の
機能に、大きな違いが出ないように頻繁にリリースされています。

..
  However, if you want to live on the edge, you can pull down the latest source
  code from our Git repository, or fork us on Github. The :doc:`installation`
  page has details for how to access the source code.

もしあなたが新しもの好きならば、最新のソースコードを Git リポジトリから
取得したり、Github からフォークすることも可能です。 :doc:`installation`
ページでは、ソースコードの参照方法についても詳しく記述しています。


..
  Development
  ===========

開発
====

..
  Any hackers interested in improving Fabric (or even users interested in how
  Fabric is put together or released) please see the :doc:`development` page. It
  contains comprehensive info on contributing, repository layout, our release
  strategy, and more.

Fabric を改良したいと思うハッカーならば(もしくは Fabric がどのように作
り上げられ、リリースされたりしているのかに興味のあるユーザーならば)
:doc:`development` ページを参照して下さい。このページには、プロジェクト
への参加のしかた、リポジトリのレイアウト、リリース計画などについての
総合的な情報が載っています。


.. _documentation-index:

.. 
  Documentation
  =============

ドキュメントについて
====================

..
  Please note that all documentation is currently written with Python 2.5 users
  in mind, but with an eye for eventual Python 3.x compatibility. This leads to
  the following patterns that may throw off readers used to Python 2.4 or who
  have already upgraded to Python 2.6:

全てのドキュメントは、現在 Python 2.5 ユーザーを対象に書かれていますが、
来たるべき Python 3.x との互換性にも気を配っています。

..
  This leads to the following patterns that may throw off readers used to Python 2.4 or who
  have already upgraded to Python 2.6:

これは、以下のパターンのように、Python 2.4 を使用している、または既に
Python 2.6 に移行している読者を混乱させるかもしれません:

..
  * ``from __future__ import with_statement``: a "future import" required to
    use the ``with`` statement in Python 2.5 -- a feature you'll be using
    frequently. Python 2.6 users don't need to do this.
  * ``<true_value> if <expression> else <false_value>``: Python's relatively new
    ternary statement, available in 2.5 and newer. Python 2.4 and older used to
    fake this with ``<expression> and <true_value> or <false_value>`` (which
    isn't quite the same thing and has some logical loopholes.)
  * ``print(<expression>)`` instead of ``print <expression>``: We use the
    ``print`` statement's optional parentheses where possible, in order to be
    more compatible with Python 3.x (in which ``print`` becomes a function.)

* ``from __future__ import with_statement``: Python 2.5 では ``with``
  文を使うには "future import" する必要があります -- これは頻繁に使うと
  思います。Python 2.6 ユーザーはこれを行なう必要はありません。
* ``<true_value> if <expression> else <false_value>``: Python の比較的
  新しい三項演算構文が 2.5 以降から利用できます。Python 2.4 以前では
  ``<expression> and <true_value> or <false_value>`` を代わりに使っていま
  した。(これは全く同じ挙動ではありませんし、論理的な穴があります)
* ``print <expression>`` ではなく ``print(<expression>)`` : Python 3.x
  との互換性のため、可能な箇所では ``print`` 文のオプションである括弧を
  使っています。(Python 3.x では ``print`` は関数になりました)

.. toctree::
    :hidden:

    tutorial
    installation
    development
    faq

.. 
  Tutorial
  --------

チュートリアル
--------------

..
  For new users, and/or for an overview of Fabric's basic functionality, please
  see the :doc:`tutorial`. The rest of the documentation will assume you're
  at least passingly familiar with the material contained within.

..
  新規のユーザーならば、そして/または Fabric の基本機能を概観するならば、 :doc:`tutorial` を参照して下さい。

For new users, and/or for an overview of Fabric's basic functionality, please see the :doc:`tutorial`. 
The rest of the documentation will assume you're at least passingly familiar with the material contained within.

.. _usage-docs:

..
  Usage documentation
  -------------------

使用方法
--------

The following list contains all major sections of Fabric's prose (non-API)
documentation, which expands upon the concepts outlined in the
:doc:`tutorial` and also covers advanced topics.

.. toctree::
    :maxdepth: 1
    :glob:

    usage/*

.. _faq:

FAQ
---

Some frequently encountered questions, coupled with answers/solutions/excuses,
may be found on the :doc:`faq` page.

.. _api_docs:

..
  API documentation
  -----------------

API ドキュメント
----------------

Fabric maintains two sets of API documentation, autogenerated from the source
code's docstrings (which are typically very thorough.)

.. _core-api:

Core API
~~~~~~~~

The **core** API is loosely defined as those functions, classes and methods
which form the basic building blocks of Fabric (such as
`~fabric.operations.run` and `~fabric.operations.sudo`) upon which everything
else (the below "contrib" section, and user fabfiles) builds.

.. toctree::
    :maxdepth: 1
    :glob:

    api/core/*

.. _contrib-api:

Contrib API
~~~~~~~~~~~

Fabric's **contrib** package contains commonly useful tools (often merged in
from user fabfiles) for tasks such as user I/O, modifying remote files, and so
forth. While the core API is likely to remain small and relatively unchanged
over time, this contrib section will grow and evolve (while trying to remain
backwards-compatible) as more use-cases are solved and added.

.. toctree::
    :maxdepth: 1
    :glob:

    api/contrib/*

..
  Changes from previous versions
  ------------------------------

前バージョンからの変更
----------------------

.. toctree::
    :maxdepth: 1
    :glob:

    changes/*

..
  Getting help
  ============

助けを得るには
==============

If you've scoured the :ref:`prose <usage-docs>` and :ref:`API <api_docs>`
documentation and still can't find an answer to your question, below are
various support resources that should help. We do request that you do at least
skim the documentation before posting tickets or mailing list questions,
however!

..
  Mailing list
  ------------

メーリングリスト
----------------

The best way to get help with using Fabric is via the `fab-user mailing list
<http://lists.nongnu.org/mailman/listinfo/fab-user>`_ (currently hosted at
``nongnu.org``.) The Fabric developers do their best to reply promptly, and the
list contains an active community of other Fabric users and contributors as
well.

.. _bugs:

..
  Bugs/ticket tracker
  -------------------

バグ/チケットトラッカ
---------------------

To file new bugs or search existing ones, you may visit Fabric's `Redmine
<http://redmine.org>`_ instance, located at `code.fabfile.org
<http://code.fabfile.org>`_. Due to issues with spam, you'll need to (quickly
and painlessly) register an account in order to post new tickets.

IRC
---

We maintain a semi-official IRC channel at ``#fabric`` on Freenode
(``irc://irc.freenode.net``) where the developers and other users may be found.
As always with IRC, we can't promise immediate responses, but some folks keep
logs of the channel and will try to get back to you when they can.

Wiki
----

There is an official Fabric `MoinMoin <http://moinmo.in>`_ wiki reachable at
`wiki.fabfile.org <http://wiki.fabfile.org>`_, although as of this writing its
usage patterns are still being worked out. Like the ticket tracker, spam has
forced us to put anti-spam measures up: the wiki has a simple, easy captcha in
place on the edit form.
