========
 Fabric
========

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

新規のユーザーならば、そして/または Fabric の基本機能を概観するならば
:doc:`tutorial` を参照して下さい。このドキュメントによって、おおまかに
Fabric を構成している機能を理解することができると思います。

.. _usage-docs:

..
  Usage documentation
  -------------------

使用方法について
----------------

..
  The following list contains all major sections of Fabric's prose (non-API)
  documentation, which expands upon the concepts outlined in the
  :doc:`tutorial` and also covers advanced topics.

次のリストは :doc:`tutorial` における概要を更に掘り下げ、より上級的な
トピックスについてもカバーした Fabric の散文的な(non-API な)ドキュメント
の全主要項目になります。

.. toctree::
    :maxdepth: 1
    :glob:

    usage/*

.. _faq:

FAQ
---

..
  Some frequently encountered questions, coupled with answers/solutions/excuses,
  may be found on the :doc:`faq` page.

よくある質問や、そに対する答え/解決方法/説明については :doc:`faq` ページを参照して下さい。

.. _api_docs:

..
  API documentation
  -----------------

API ドキュメント
----------------

..
  Fabric maintains two sets of API documentation, autogenerated from the source
  code's docstrings (which are typically very thorough.)

Fabric は、ソースコードの docstring (通常は詳細に記述されています)から
自動生成された、2 セットの API ドキュメントを保持しています。

.. _core-api:

Core API
~~~~~~~~

..
  The **core** API is loosely defined as those functions, classes and methods
  which form the basic building blocks of Fabric (such as
  `~fabric.operations.run` and `~fabric.operations.sudo`) upon which everything
  else (the below "contrib" section, and user fabfiles) builds.

**core** API は、Fabric のその他全ての構造(次の "contrib" セクションや
ユーザーの fab ファイルなど)を構成する(`~fabric.operations.run` や
`~fabric.operations.sudo` のような)基本構造ブロックの関数、クラス、
メソッドとして、ゆるく定義されています。

.. toctree::
    :maxdepth: 1
    :glob:

    api/core/*

.. _contrib-api:

Contrib API
~~~~~~~~~~~

..
  Fabric's **contrib** package contains commonly useful tools (often merged in
  from user fabfiles) for tasks such as user I/O, modifying remote files, and so
  forth. While the core API is likely to remain small and relatively unchanged
  over time, this contrib section will grow and evolve (while trying to remain
  backwards-compatible) as more use-cases are solved and added.

Fabric の **contrib** パッケージは、ユーザーI/O、リモートファイル修正
などのタスクのための、汎用的で有用なツール群です(よくユーザーの fab
ファイルからマージされます)。core API は、小さいまま比較的長い期間は変更
させない方が適当ですが、この contrib セクションは、より多くのユースケースが
解決/追加できるように(後方互換性を保つようにはしますが)成長、進化させて
いきます。

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

..
  If you've scoured the :ref:`prose <usage-docs>` and :ref:`API <api_docs>`
  documentation and still can't find an answer to your question, below are
  various support resources that should help. We do request that you do at least
  skim the documentation before posting tickets or mailing list questions,
  however!

もし :ref:`prose <usage-docs>` や :ref:`API <api_docs>` ドキュメントを
漁ってもあなたの疑問が解決できないならば、次のような様々なサポート手段が
役に立つでしょう。とはいえ、最低でもドキュメントをざっと調べてから、
チケットやメーリングリストに質問を投稿して下さいね！

..
  Mailing list
  ------------

メーリングリスト
----------------

..
  The best way to get help with using Fabric is via the `fab-user mailing list
  <http://lists.nongnu.org/mailman/listinfo/fab-user>`_ (currently hosted at
  ``nongnu.org``.) The Fabric developers do their best to reply promptly, and the
  list contains an active community of other Fabric users and contributors as
  well.

Fabric の利用に関して助けを得るには `fab-user メーリングリスト
<http://lists.nongnu.org/mailman/listinfo/fab-user>`_ (現在は
``nongnu.org`` にホスティングされています)が一番でしょう。Fabric の
開発者はできるだけ早く返信しようとしてくれますし、メーリングリスト内では
他の Fabric ユーザーやコントリビュータ達が活発なコミュニティを形成しています。

.. _bugs:

..
  Bugs/ticket tracker
  -------------------

バグ/チケットトラッカ
---------------------

..
  To file new bugs or search existing ones, you may visit Fabric's `Redmine
  <http://redmine.org>`_ instance, located at `code.fabfile.org
  <http://code.fabfile.org>`_. Due to issues with spam, you'll need to (quickly
  and painlessly) register an account in order to post new tickets.

新しいバグを登録したり、既存のバグを検索するには `code.fabfile.org
<http://code.fabfile.org>`_ にある Fabric の `Redmine
<http://redmine.org>`_ インスタンスを見てみるといいでしょう。スパム投稿を
防ぐため、新しいチケットを投稿するには(時間もかからず簡単な)アカウント
登録が必要です。

IRC
---

..
  We maintain a semi-official IRC channel at ``#fabric`` on Freenode
  (``irc://irc.freenode.net``) where the developers and other users may be found.
  As always with IRC, we can't promise immediate responses, but some folks keep
  logs of the channel and will try to get back to you when they can.

Freenode (``irc://irc.freenode.net``)において、半オフィシャルの IRC
チャンネル``#fabric`` を保持しているので、そこで開発者や他のユーザーを
見付けることができるでしょう。IRC ではいつものことながら、即時の回答を
約束することはできませんが、一部の人達がチャンネルのログを保存して、
可能な時に返答しようとしてくれるでしょう。

Wiki
----

..
  There is an official Fabric `MoinMoin <http://moinmo.in>`_ wiki reachable at
  `wiki.fabfile.org <http://wiki.fabfile.org>`_, although as of this writing its
  usage patterns are still being worked out. Like the ticket tracker, spam has
  forced us to put anti-spam measures up: the wiki has a simple, easy captcha in
  place on the edit form.

`wiki.fabfile.org <http://wiki.fabfile.org>`_ にオフィシャル Fabric
`MoinMoin <http://moinmo.in>`_ wiki があります。この文章を書いている
時点の話ですが、今のところ使用パターンとしてうまくいっています。チケット
トラッカーのように、スパム対策の導入を余儀なくされていますが、 wiki では
編集フォームにシンプルで簡単なキャプチャを導入しています。
