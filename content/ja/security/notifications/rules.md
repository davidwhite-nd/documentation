---
aliases:
- /ja/security_platform/notification_profiles/
- /ja/security_platform/notification_rules/
- /ja/security_platform/notifications/rules/
- /ja/security/notification_profiles/
- /ja/security/notification_rules/
description: 通知ルールを作成し、セキュリティ検出ルールがトリガーされたときに、チームとインテグレーションに自動的に通知します。
further_reading:
- link: /security/detection_rules/
  tag: ドキュメント
  text: セキュリティ検出ルールについて
kind: documentation
title: ルール
---

## 概要

セキュリティ通知ルールは、個々のセキュリティ検出ルールの通知設定を手動で編集することなく、チームに問題を通知する重要な役割を果たします。

重大度、ルールタイプ、ルールタグ、シグナル属性、シグナルタグなどのパラメーターに基づいて、複数のセキュリティ検出ルールとシグナルにまたがる通知プリファレンスを通知ルール内で作成および変更することができます。

**Notification Rules** ページで、作成されたすべての通知ルールを閲覧、検索することができます。組織内のユーザーが作成した通知ルールを作成、編集、クローン、有効化、無効化、削除、または表示することができます。

{{< img src="security/notification-profiles-overview.png" alt="通知ルール" style="width:100%;" >}}

## 通知ルールの作成

新規に通知ルールを作成する場合は、以下の手順で行ってください。

1. Datadog で、**Security** > **Setup & Configuration** にある [Notification Rules タブ][1]に移動します。
2. ページ右上の **+ New Notification Rule** ボタンをクリックします。
3. **Name** フィールドに通知ルールの名前を入力します。
4. セキュリティ検出ルールやセキュリティシグナルに一致する条件によって、この通知ルールがトリガーされる場合のロジックを定義します。
    - セキュリティ検出ルールの場合、重大度、ルールタイプ、ルールタグを条件として通知ルールを作成することができます。
    - セキュリティ信号の場合、信号の属性とシグナルタグが一致すれば、通知ルールを作成することができます。

    例えば、重大度を `Medium` に設定すると、ステップ 4 で設定したセキュリティシグナルのルール条件を少なくとも 1 回満たしている限り、シグナルが有効な通知ルールをトリガーすることを意味します。

5. **Recipients** フィールドで、通知したい関係者をすべて選択します。例えば、個人、チーム、リスト、ハンドルネームに通知します。
6. 通知ルールに一致するルールのプレビューパネルが右側に表示され、通知ルールが具体的すぎるか広範すぎるかを示すのに役立ちます。
7. **Save and Activate** をクリックすると、通知ルールが保存されます。これで通知ルールが自動的にアクティブになり、メインの **Notification Rules** ページに戻ります。

{{< img src="security/notification-profiles-setup.png" alt="通知ルールの設定" style="width:100%;" >}}

通知ルールがセキュリティ検出ルールと関連付けられている場合、ルールの “Set severity and notifications” (重大度と通知の設定) セクションでルールのトリガー条件を確認することができます。

通知ルールが設定された条件に一致する場合、結果の通知には、一致した通知ルールに関する詳細が通知フッターに含まれます。

## 通知ルールの管理

### 検索

フリーテキスト検索は、**Notification Rule** ページにあるテキストで通知ルールをフィルタリングします。ルールタイプ、ルールタグ、シグナル属性、シグナルタグ内のタグを選択すると、検索にそのタグが追加され、その値に一致する通知ルールが表示されます。

検索クエリを編集すると、検索結果がリアルタイムで更新されます。**Search** ボタンはありません。

### 有効または無効にする

通知ルールカードの右上にあるトグルスイッチで、通知ルールを有効または無効にします。

### 編集

通知ルールを編集するには、通知ルールカードにカーソルを合わせ、クリックします。

### Clone

通知ルールを複製するには、通知ルールカードの右上にあるケバブメニューをクリックし、メニューから **Clone Notification Rule** を選択します。

### 削除

通知ルールを削除するには、通知ルールカードの右上にあるケバブメニューをクリックし、メニューから **Delete Notification Rule** を選択します。

## その他の参考資料

{{< partial name="whats-next/whats-next.html" >}}

[1]: https://app.datadoghq.com/security/configuration/notification-profiles