[![GitHub issues](https://img.shields.io/github/issues/0ta2/php_role)](https://github.com/0ta2/php_role/issues)
[![GitHub stars](https://img.shields.io/github/stars/0ta2/php_role)](https://github.com/0ta2/php_role/stargazers)
![GitHub Actions](https://github.com/0ta2/php_role/workflows/Molecule%20Test/badge.svg)

php_role
=========

PHPをインストールするためのロールです。

Requirements
------------

特になし。

Role Variables
--------------

| 変数名              | 役割                           |
|---------------------|--------------------------------|
| php_install_package | phpの基本パッケージを指定      |
| php_packages_extra  | 追加の php package を定義      |
| php_conf_d_dir      | conf.d の場所を定義            |
| php_ini             | php.ini に追加したい項目を定義 |
| php_enable_repo     | Remi等のリポジトリを定義する   |


`php.ini` は、下記の用に `section`, `option`, `value` で設定を記載すれば、`99-php.ini` というファイル名で配置されます。

デフォルトの `Timezone` は、`Asia/Tokyo` になっています。

```
php_ini:
 - { section: "Date", option: "date.timezone", value: "Asia/Tokyo" }
```

`php_enable_repo` は、[0ta2/repo_remi_role](https://github.com/0ta2/repo_remi_role)を使いRemiリポジトリを有効にしてから下記のように設定しご利用ください。

```
php_enable_repo: "remi,remi-php73"
```

Dependencies
------------

特になし

Example Playbook
----------------

```
---
    - hosts: servers
      roles:
         - { role: 0ta2.php_remi_repo }
         - { role: 0ta2.php_role }
```

License
-------

![GitHub](https://img.shields.io/github/license/0ta2/php_role)
