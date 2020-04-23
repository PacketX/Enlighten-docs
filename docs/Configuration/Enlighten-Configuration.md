Enlighten Configuration
==================

完整的`Enlighten`設定很大，`Nethook`和`Listening`皆為陣列，每個`Nethook`和`Listening`都是獨立的tab頁面，請參考[05.Template](05.Template.md#config_view)；`Launch`和`Reload`需要完整全部帶上；雖然後台也會檢查參數，但前台最好也做基本檢查。

Example
-----------

```
{
    "MessageLog": true,
    "ErrorLog": true,

    "Nethook": [
        {
            "xxxx": xxxx
            "xxxx": xxxx
            ....
        },
        {
            "xxxx": xxxx
            "xxxx": xxxx
            ....
        }
    ],
    "Listening": [
        {
            "xxxx": xxxx
            "xxxx": xxxx
            ....
        },
        {
            "xxxx": xxxx
            "xxxx": xxxx
            ....
        }
    ]
}
```

Configuration
------------

`Key`是Json中的名字；`Prompt`是顯示在網頁上的名字，`-`表示不顯示；`Style`是建議用的顯示方式，可以用其他方案代替；有些設定並不會出現（[`GET` `/template/config`](05.Template.md#config)），以有傳回的值為準。

<h3>Core</h3>

|      Key     |    Prompt   | Json Type |     Style     |                   Validation                   |            Note            |
|:------------:|:-----------:|:---------:|:-------------:|:----------------------------------------------:|:--------------------------:|
|  MessageLog  | Message Log |  Boolean  |    Checkbox   |                        -                       |              -             |
|   ErrorLog   |  Error Log  |  Boolean  |    Checkbox   |                        -                       |              -             |
