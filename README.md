# apkparser
android apk file parser tools

### Installation

Run the following in your command-line:

```shell
$ brew tap wswenyue/apkparser && brew install apkparser
```

### How to use

```shell
$ apkparser -h

usage: h
 -amstart       adb am start app intent String
 -apk <arg>     the apk file path
 -apn           the app applicationName
 -h             help
 -info          show all info
 -kalgid        the app key sign algIdName
 -kinfo         show apk key info
 -kinterval     the app key interval
 -kissuer       the app key issuer
 -kserialno     the app key serialNumber
 -ksignmd5      the app key sign md5
 -ksignsha1     the app key sign sha1
 -ksignsha256   the app key sign sha256
 -ksubject      the app key subject
 -launcher      the app launcher [first Activity in launchers]
 -launchers     the app launchers
 -name          the app name
 -pn            the app packageName
 -vc            the app versionCode
 -vn            the app versionName
```

eg:

```shell
$ apkparser -apk testapp.apk
```
result:
```json
{
	"activities":[...],
	"appName":"@2131165218",
	"debuggable":"false",
	"keyInfo":{
		"algIdName":"SHA256withRSA",
		"interval":"Wed Jul 05 14:15:05 CST 2017--Thu Apr 07 14:15:05 CST 2072",
		"issuer":"CN=Wenyue, OU=Ws, O=Ws, L=CN, ST=BJ, C=CN",
		"serialNumber":"2a7c48ce",
		"sign_md5":"6D:15:B6:36:99:10:23:FC:87:9A:0A:26:DD:65:FB:D3",
		"sign_sha1":"FC:7E:6C:CE:60:0D:8E:0D:17:58:DA:4D:01:71:A7:BE:09:C0:3A:29",
		"sign_sha256":"F5:7C:6E:34:F0:AD:82:F6:9C:09:09:AA:88:09:26:A4:C9:F5:3E:74:68:C4:62:2A:FC:9D:9F:5A:28:56:8A:B7",
		"subject":"CN=Wenyue, OU=Ws, O=Ws, L=CN, ST=BJ, C=CN",
		"version":3
	},
	"launchers":[
		{
			"intentFilter":{
				"actions":[{
					"name":"android.intent.action.MAIN"
				}],
				"categories":[{
					"name":"android.intent.category.LAUNCHER"
				}]
			},
			"name":"win.wswenyue.helloandroid.MainActivity"
		}
	],
	"packageName":"win.wswenyue.helloandroid",
	"versionCode":"1",
	"versionName":"1.0"
}
```