<p align="center"> 
  <br/>
  <a href="https://opensource.org/license/agpl-v3"><img src="https://img.shields.io/badge/License-AGPL_v3-blue.svg?color=3F51B5&style=for-the-badge&label=License&logoColor=000000&labelColor=ececec" alt="License: AGPLv3"></a>
  <a href="https://discord.immich.app">
    <img src="https://img.shields.io/discord/979116623879368755.svg?label=Discord&logo=Discord&style=for-the-badge&logoColor=000000&labelColor=ececec" alt="Discord"/>
  </a>
  <br/>
  <br/>
</p>

<p align="center">
<img src="design/immich-logo-stacked-light.svg" width="300" title="Login With Custom URL">
</p>
<h3 align="center">高性能AI产品图自托管，照片和视频管理解决方案</h3>
分支特点：
| 支持AI以图搜图，支持中文搜索图片和视频
| 便捷搜索和信息展示
| 支持主线的手机APP
<br/>

<a href="https://immich.app">
<img src="design/immich-screenshots.png" title="Main Screenshot">
</a>
<br/>

<p align="center">
  <a href="readme_i18n/README_ca_ES.md">Català</a>
  <a href="readme_i18n/README_es_ES.md">Español</a>
  <a href="readme_i18n/README_fr_FR.md">Français</a>
  <a href="readme_i18n/README_it_IT.md">Italiano</a>
  <a href="readme_i18n/README_ja_JP.md">日本語</a>
  <a href="readme_i18n/README_ko_KR.md">한국어</a>
  <a href="readme_i18n/README_de_DE.md">Deutsch</a>
  <a href="readme_i18n/README_nl_NL.md">Nederlands</a>
  <a href="readme_i18n/README_tr_TR.md">Türkçe</a>
  <a href="readme_i18n/README_zh_CN.md">简体中文</a>
  <a href="readme_i18n/README_zh_TW.md">正體中文</a>
  <a href="readme_i18n/README_uk_UA.md">Українська</a>
  <a href="readme_i18n/README_ru_RU.md">Русский</a>
  <a href="readme_i18n/README_pt_BR.md">Português Brasileiro</a>
  <a href="readme_i18n/README_sv_SE.md">Svenska</a>
  <a href="readme_i18n/README_ar_JO.md">العربية</a>
  <a href="readme_i18n/README_vi_VN.md">Tiếng Việt</a>
  <a href="readme_i18n/README_th_TH.md">ภาษาไทย</a>
</p>


> [!WARNING]
> ⚠️ Always follow [3-2-1](https://www.backblaze.com/blog/the-3-2-1-backup-strategy/) backup plan for your precious photos and videos!
> 
 


## Features

| Features                                     | Mobile | Web |
| :------------------------------------------- | ------ | --- |
| Upload and view videos and photos            | Yes    | Yes |
| Auto backup when the app is opened           | Yes    | N/A |
| Prevent duplication of assets                | Yes    | Yes |
| Selective album(s) for backup                | Yes    | N/A |
| Download photos and videos to local device   | Yes    | Yes |
| Multi-user support                           | Yes    | Yes |
| Album and Shared albums                      | Yes    | Yes |
| Scrubbable/draggable scrollbar               | Yes    | Yes |
| Support raw formats                          | Yes    | Yes |
| Metadata view (EXIF, map)                    | Yes    | Yes |
| Search by metadata, objects, faces, and CLIP | Yes    | Yes |
| Administrative functions (user management)   | No     | Yes |
| Background backup                            | Yes    | N/A |
| Virtual scroll                               | Yes    | Yes |
| OAuth support                                | Yes    | Yes |
| API Keys                                     | N/A    | Yes |
| LivePhoto/MotionPhoto backup and playback    | Yes    | Yes |
| Support 360 degree image display             | No     | Yes |
| User-defined storage structure               | Yes    | Yes |
| Public Sharing                               | Yes    | Yes |
| Archive and Favorites                        | Yes    | Yes |
| Global Map                                   | Yes    | Yes |
| Partner Sharing                              | Yes    | Yes |
| Facial recognition and clustering            | Yes    | Yes |
| Memories (x years ago)                       | Yes    | Yes |
| Offline support                              | Yes    | No  |
| Read-only gallery                            | Yes    | Yes |
| Stacked Photos                               | Yes    | Yes |
| Tags                                         | No     | Yes |
| Folder View                                  | Yes    | Yes |



Docker Compose 安装
Docker Compose 是运行 Immich 的推荐方法。以下是使用 Docker Compose 部署 Immich 的步骤。

步骤1 - 下载所需文件
创建一个你选择的目录（例如 ）来存放 and 文件。./immich-appdocker-compose.yml.env

移动到你创建的目录
mkdir ./immich-app
cd ./immich-app

通过执行以下命令下载docker-compose.yml和 example.env：

拿docker-compose.yml档案
wget -O docker-compose.yml https://github.com/benpuzzle2/immich/tree/main/docker/docker-compose.yml

获取.env文件
wget -O .env https://github.com/benpuzzle2/immich/tree/main/docker/example.env

你也可以从浏览器下载这两个文件，并将它们移到你创建的目录中，确保将重命名为 。example.env.env

步骤2 - 用自定义值填充.env文件
默认环境变量内容
# You can find documentation for all the supported env variables at https://docs.immich.app/install/environment-variables
# The location where your uploaded files are stored
UPLOAD_LOCATION=./library
# The location where your database files are stored. Network shares are not supported for the database
DB_DATA_LOCATION=./postgres
# To set a timezone, uncomment the next line and change Etc/UTC to a TZ identifier from this list: https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List
TZ=Asia/Shanghai

# The Immich version to use. You can pin this to a specific version like "v2.1.0"
IMMICH_VERSION=v2
# Connection secret for postgres. You should change it to a random password
# Please use only the characters `A-Za-z0-9`, without special characters or spaces
DB_PASSWORD=postgres
# The values below this line do not need to be changed
###################################################################################
DB_USERNAME=postgres
DB_DATABASE_NAME=immich


Populate with your preferred location for storing backup assets. It should be a new directory on the server with enough free space.UPLOAD_LOCATION
Consider changing to a custom value. Postgres is not publicly exposed, so this password is only used for local authentication. To avoid issues with Docker parsing this value, it is best to use only the characters . is a handy utility for this.DB_PASSWORDA-Za-z0-9pwgen
Set your timezone by uncommenting the line.TZ=
Populate custom database information if necessary.

开始容器
docker compose up -d

Docker 版本
如果你遇到诸如 或 这样的错误，你很可能运行的是错误的 Docker 版本。（例如，Ubuntu 22.04.3 LTS 中的 docker.io 包就会出现这种情况。）你可以通过按照你发行版的完整 Docker Engine 安装流程来纠正这个问题，关键是“卸载旧版本”和“使用apt/rpm repository安装”部分。这些程序会用 Docker 官方包替换发行版的 Docker 包。unknown shorthand flag: 'd' in -dopen <location of your .env file>: permission denied

注意正确的命令实际上是 ，而不是 。如果你在纯版Ubuntu 22.04上尝试后者，它会以不同的方式失败：docker composedocker-compose

The Compose file './docker-compose.yml' is invalid because:
'name' does not match any of the regexes: '^x-'

请参见上一段关于从官方 Docker 仓库安装的相关内容。

健康检查开始间隔
如果出现错误，建议在文件部分注释 for 的行。can't set healthcheck.start_interval as feature require Docker Engine v25 or laterstart_intervaldatabasedocker-compose.yml
