<div class="Box-sc-g0xbh4-0 bJMeLZ js-snippet-clipboard-copy-unpositioned" data-hpc="true"><article class="markdown-body entry-content container-lg" itemprop="text"><ul dir="auto">
<li><a href="#overview"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">概述</font></font></a></li>
<li><a href="#functionality"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">功能性</font></font></a></li>
<li><a href="#recommended-system-requirements"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">推荐系统要求</font></font></a></li>
<li><a href="#running-docker-image"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">运行 Docker 镜像</font></font></a></li>
<li><a href="#configuring-docker-image"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">配置 Docker 镜像</font></font></a>
<ul dir="auto">
<li><a href="#storing-data"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">存储数据</font></font></a></li>
<li><a href="#running-onlyoffice-document-server-on-different-port"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在不同端口上运行 ONLYOFFICE 文档服务器</font></font></a></li>
<li><a href="#running-onlyoffice-document-server-using-https"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用 HTTPS 运行 ONLYOFFICE 文档服务器</font></font></a>
<ul dir="auto">
<li><a href="#generation-of-self-signed-certificates"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">自签名证书的生成</font></font></a></li>
<li><a href="#strengthening-the-server-security"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">加强服务器安全</font></font></a></li>
<li><a href="#installation-of-the-ssl-certificates"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SSL 证书的安装</font></font></a></li>
<li><a href="#available-configuration-parameters"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可用的配置参数</font></font></a></li>
</ul>
</li>
</ul>
</li>
<li><a href="#installing-onlyoffice-document-server-integrated-with-community-and-mail-servers"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装与社区和邮件服务器集成的 ONLYOFFICE 文档服务器</font></font></a></li>
<li><a href="#onlyoffice-document-server-ipv6-setup"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE文档服务器ipv6设置</font></font></a></li>
<li><a href="#issues"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">问题</font></font></a>
<ul dir="auto">
<li><a href="#docker-issues"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Docker 问题</font></font></a></li>
<li><a href="#document-server-usage-issues"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">文档服务器使用问题</font></font></a></li>
</ul>
</li>
<li><a href="#project-information"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">项目信息</font></font></a></li>
<li><a href="#user-feedback-and-support"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用户反馈和支持</font></font></a></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">概述</font></font></h2><a id="user-content-overview" class="anchor" aria-label="永久链接：概述" href="#overview"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE Document Server 是一个在线办公套件，包括文本、电子表格和演示文稿的查看器和编辑器，与 Office Open XML 格式完全兼容：.docx、.xlsx、.pptx，并支持实时协作编辑。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">从版本 6.0 开始，Document Server 作为 ONLYOFFICE Docs 分发。它有</font></font><a href="https://github.com/ONLYOFFICE/DocumentServer#onlyoffice-document-server-editions"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">三个版本</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。使用此映像，您将安装免费的社区版本。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE Docs 可用作 ONLYOFFICE Workspace 的一部分，或与第三方同步和共享解决方案（例如 Nextcloud、ownCloud、Seafile）一起使用，以在其界面内实现协作编辑。</font></font></p>
<p dir="auto"><em><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">重要</font></font></strong></em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请在使用之前更新</font></font><code>docker-engine</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">到最新版本（</font></font><code>20.10.21</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">截至撰写本文档时）。我们使用它</font></font><code>ubuntu:22.04</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">作为基础镜像，旧版本的 docker 与其存在兼容性问题</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">功能性</font></font></h2><a id="user-content-functionality" class="anchor" aria-label="永久链接：功能" href="#functionality"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE文档编辑器</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE 电子表格编辑器</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE 演示文稿编辑器</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">适用于 iOS 的 ONLYOFFICE 文档应用程序</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">协同编辑</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">象形文字支持</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">支持所有流行格式：DOC、DOCX、TXT、ODT、RTF、ODP、EPUB、ODS、XLS、XLSX、CSV、PPTX、HTML</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">将其与 ONLYOFFICE 社区服务器集成，您将能够：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">查看和编辑连接到 ONLYOFFICE 的 Drive、Box、Dropbox、OneDrive、OwnCloud 上存储的文件；</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">分享文件;</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在网站上嵌入文档；</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">管理文档的访问权限。</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">推荐系统要求</font></font></h2><a id="user-content-recommended-system-requirements" class="anchor" aria-label="永久链接：推荐的系统要求" href="#recommended-system-requirements"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<ul dir="auto">
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">内存</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：4 GB 或以上</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">CPU</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：双核 2 GHz 或更高</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">交换空间</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：至少 2 GB</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">硬盘</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：至少 2 GB 可用空间</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">发行版</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：64 位 Red Hat、CentOS 或其他内核版本 3.8 或更高版本的兼容发行版、64 位 Debian、Ubuntu 或其他内核版本 3.8 或更高版本的兼容发行版</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Docker</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：版本 1.9.0 或更高版本</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">运行 Docker 镜像</font></font></h2><a id="user-content-running-docker-image" class="anchor" aria-label="永久链接：运行 Docker 镜像" href="#running-docker-image"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>sudo docker run -i -t -d -p 80:80 onlyoffice/documentserver
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="sudo docker run -i -t -d -p 80:80 onlyoffice/documentserver" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您希望单独安装ONLYOFFICE Document Server，请使用此命令。要安装与社区和邮件服务器集成的 ONLYOFFICE 文档服务器，请参阅以下相应说明。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">配置 Docker 镜像</font></font></h2><a id="user-content-configuring-docker-image" class="anchor" aria-label="永久链接：配置 Docker 镜像" href="#configuring-docker-image"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">存储数据</font></font></h3><a id="user-content-storing-data" class="anchor" aria-label="永久链接：存储数据" href="#storing-data"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">所有数据都存储在专门指定的目录、</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">数据卷</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">中，位置如下：</font></font></p>
<ul dir="auto">
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/var/log/onlyoffice</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用于 ONLYOFFICE 文档服务器日志</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/var/www/onlyoffice/</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">证书数据</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/var/lib/onlyoffice</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用于文件缓存</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">/var/lib/postgresql</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用于数据库</font></font></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要从容器外部访问数据，您需要安装卷。可以通过在 docker run 命令中指定“-v”选项来完成。</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>sudo docker run -i -t -d -p 80:80 \
    -v /app/onlyoffice/DocumentServer/logs:/var/log/onlyoffice  \
    -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data  \
    -v /app/onlyoffice/DocumentServer/lib:/var/lib/onlyoffice \
    -v /app/onlyoffice/DocumentServer/rabbitmq:/var/lib/rabbitmq \
    -v /app/onlyoffice/DocumentServer/redis:/var/lib/redis \
    -v /app/onlyoffice/DocumentServer/db:/var/lib/postgresql  onlyoffice/documentserver
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="sudo docker run -i -t -d -p 80:80 \
    -v /app/onlyoffice/DocumentServer/logs:/var/log/onlyoffice  \
    -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data  \
    -v /app/onlyoffice/DocumentServer/lib:/var/lib/onlyoffice \
    -v /app/onlyoffice/DocumentServer/rabbitmq:/var/lib/rabbitmq \
    -v /app/onlyoffice/DocumentServer/redis:/var/lib/redis \
    -v /app/onlyoffice/DocumentServer/db:/var/lib/postgresql  onlyoffice/documentserver" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">通常，您不需要存储容器数据，因为容器的操作不依赖于其状态。保存数据将会很有用：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用于轻松访问容器数据，例如日志</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">取消容器内数据大小的限制</font></font></li>
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用容器外部启动的服务时，例如 PostgreSQL、Redis、RabbitMQ</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在不同端口上运行 ONLYOFFICE 文档服务器</font></font></h3><a id="user-content-running-onlyoffice-document-server-on-different-port" class="anchor" aria-label="永久链接：在不同端口上运行 ONLYOFFICE 文档服务器" href="#running-onlyoffice-document-server-on-different-port"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要更改端口，请使用 -p 命令。例如：要使您的门户可以通过端口 8080 访问，请执行以下命令：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>sudo docker run -i -t -d -p 8080:80 onlyoffice/documentserver
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="sudo docker run -i -t -d -p 8080:80 onlyoffice/documentserver" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用 HTTPS 运行 ONLYOFFICE 文档服务器</font></font></h3><a id="user-content-running-onlyoffice-document-server-using-https" class="anchor" aria-label="永久链接：使用 HTTPS 运行 ONLYOFFICE 文档服务器" href="#running-onlyoffice-document-server-using-https"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>    sudo docker run -i -t -d -p 443:443 \
    -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data  onlyoffice/documentserver
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="    sudo docker run -i -t -d -p 443:443 \
    -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data  onlyoffice/documentserver" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可以使用 SSL 保护对 onlyoffice 应用程序的访问，从而防止未经授权的访问。虽然 CA 认证的 SSL 证书允许通过 CA 验证信任，但只要每个客户端采取一些额外的步骤来验证您网站的身份，自签名证书也可以提供同等级别的信任验证。下面提供了实现此目的的说明。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要通过 SSL 保护应用程序，基本上需要做两件事：</font></font></p>
<ul dir="auto">
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">私钥（.key）</font></font></strong></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SSL 证书 (.crt)</font></font></strong></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">因此，您需要创建并安装以下文件：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>    /app/onlyoffice/DocumentServer/data/certs/tls.key
    /app/onlyoffice/DocumentServer/data/certs/tls.crt
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="    /app/onlyoffice/DocumentServer/data/certs/tls.key
    /app/onlyoffice/DocumentServer/data/certs/tls.crt" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">当使用 CA 认证的证书（例如</font></font><a href="https://letsencrypt.org" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Let's encrypt</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">）时，这些文件由 CA 提供给您。如果您使用自签名证书，则需要</font></font><a href="#generation-of-self-signed-certificates"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">自己</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">生成这些文件。</font></font></p>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用自动生成的 Let's Encrypt SSL 证书</font></font></h4><a id="user-content-using-the-automatically-generated-lets-encrypt-ssl-certificates" class="anchor" aria-label="永久链接：使用自动生成的 Let's Encrypt SSL 证书" href="#using-the-automatically-generated-lets-encrypt-ssl-certificates"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>    sudo docker run -i -t -d -p 80:80 -p 443:443 \
    -e LETS_ENCRYPT_DOMAIN=your_domain -e LETS_ENCRYPT_MAIL=your_mail  onlyoffice/documentserver
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="    sudo docker run -i -t -d -p 80:80 -p 443:443 \
    -e LETS_ENCRYPT_DOMAIN=your_domain -e LETS_ENCRYPT_MAIL=your_mail  onlyoffice/documentserver" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您想自动获取并扩展 Let's Encrypt SSL 证书，只需设置 LETS_ENCRYPT_DOMAIN 和 LETS_ENCRYPT_MAIL 变量即可。</font></font></p>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">自签名证书的生成</font></font></h4><a id="user-content-generation-of-self-signed-certificates" class="anchor" aria-label="永久链接：生成自签名证书" href="#generation-of-self-signed-certificates"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">自签名 SSL 证书的生成涉及一个简单的 3 步过程。</font></font></p>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第 1 步</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：创建服务器私钥</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>openssl genrsa -out tls.key 2048</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="openssl genrsa -out tls.key 2048" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第 2 步</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：创建证书签名请求 (CSR)</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>openssl req -new -key tls.key -out tls.csr</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="openssl req -new -key tls.key -out tls.csr" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第 3 步</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：使用私钥和 CSR 签署证书</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>openssl x509 -req -days 365 -in tls.csr -signkey tls.key -out tls.crt</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="openssl x509 -req -days 365 -in tls.csr -signkey tls.key -out tls.crt" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您现在已经生成了 365 天有效的 SSL 证书。</font></font></p>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">加强服务器安全</font></font></h4><a id="user-content-strengthening-the-server-security" class="anchor" aria-label="永久链接：加强服务器安全" href="#strengthening-the-server-security"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">本节为您提供</font></font><a href="https://raymii.org/s/tutorials/Strong_SSL_Security_On_nginx.html" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">加强服务器安全性的</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">说明。为了实现这一点，您需要生成更强的 DHE 参数。</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>openssl dhparam -out dhparam.pem 2048</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="openssl dhparam -out dhparam.pem 2048" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SSL 证书的安装</font></font></h4><a id="user-content-installation-of-the-ssl-certificates" class="anchor" aria-label="永久链接：SSL 证书的安装" href="#installation-of-the-ssl-certificates"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在上面生成的四个文件中，您需要</font><font style="vertical-align: inherit;">在 onlyoffice 服务器上安装</font></font><code>tls.key</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">、</font></font><code>tls.crt</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">和文件。</font></font><code>dhparam.pem</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">不需要 CSR 文件，但请确保安全备份该文件（以防再次需要它）。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">onlyoffice 应用程序配置为查找 SSL 证书的默认路径位于，但是可以使用</font><font style="vertical-align: inherit;">、</font><font style="vertical-align: inherit;">和</font><font style="vertical-align: inherit;">配置选项</font></font><code>/var/www/onlyoffice/Data/certs</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">更改此路径。</font></font><code>SSL_KEY_PATH</code><font style="vertical-align: inherit;"></font><code>SSL_CERTIFICATE_PATH</code><font style="vertical-align: inherit;"></font><code>SSL_DHPARAM_PATH</code><font style="vertical-align: inherit;"></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">该</font></font><code>/var/www/onlyoffice/Data/</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">路径是数据存储的路径，这意味着您必须在其中创建一个名为 certs 的文件夹</font></font><code>/app/onlyoffice/DocumentServer/data/</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">并将文件复制到其中，作为安全措施，您将更新文件的权限</font></font><code>tls.key</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以仅由所有者读取。</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>mkdir -p /app/onlyoffice/DocumentServer/data/certs
cp tls.key /app/onlyoffice/DocumentServer/data/certs/
cp tls.crt /app/onlyoffice/DocumentServer/data/certs/
cp dhparam.pem /app/onlyoffice/DocumentServer/data/certs/
chmod 400 /app/onlyoffice/DocumentServer/data/certs/tls.key</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="mkdir -p /app/onlyoffice/DocumentServer/data/certs
cp tls.key /app/onlyoffice/DocumentServer/data/certs/
cp tls.crt /app/onlyoffice/DocumentServer/data/certs/
cp dhparam.pem /app/onlyoffice/DocumentServer/data/certs/
chmod 400 /app/onlyoffice/DocumentServer/data/certs/tls.key" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您现在距离保护我们的应用程序仅一步之遥。</font></font></p>
<div class="markdown-heading" dir="auto"><h4 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">可用的配置参数</font></font></h4><a id="user-content-available-configuration-parameters" class="anchor" aria-label="永久链接：可用的配置参数" href="#available-configuration-parameters"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><em><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请参阅 docker run 命令选项以获取</font></font><code>--env-file</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">标志，您可以在其中在单个文件中指定所有必需的环境变量。这将使您免于编写可能很长的 docker run 命令。</font></font></em></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下是可以使用环境变量设置的参数的完整列表。</font></font></p>
<ul dir="auto">
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE_HTTPS_HSTS_ENABLED</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：用于关闭 HSTS 配置的高级配置选项。仅当使用 SSL 时适用。默认为</font></font><code>true</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE_HTTPS_HSTS_MAXAGE</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：用于在 onlyoffice nginx vHost 配置中设置 HSTS max-age 的高级配置选项。仅当使用 SSL 时适用。默认为</font></font><code>31536000</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SSL_CERTIFICATE_PATH</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：要使用的 SSL 证书的路径。默认为</font></font><code>/var/www/onlyoffice/Data/certs/tls.crt</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SSL_KEY_PATH</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：SSL 证书私钥的路径。默认为</font></font><code>/var/www/onlyoffice/Data/certs/tls.key</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SSL_DHPARAM_PATH</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：Diffie-Hellman 参数的路径。默认为</font></font><code>/var/www/onlyoffice/Data/certs/dhparam.pem</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SSL_VERIFY_CLIENT</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：使用该文件启用客户端证书验证</font></font><code>CA_CERTIFICATES_PATH</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。默认为</font></font><code>false</code></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DB_TYPE</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：数据库类型。支持的值为</font></font><code>postgres</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">,</font></font><code>mariadb</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><code>mysql</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。默认为</font></font><code>postgres</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DB_HOST</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：运行数据库服务器的主机的 IP 地址或名称。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DB_PORT</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：数据库服务器端口号。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DB_NAME</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：要使用的数据库的名称。应该在容器启动时存在。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DB_USER</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：具有数据库帐户超级用户权限的新用户名。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">DB_PWD</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：为数据库帐户设置的密码。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">AMQP_URI</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：</font><font style="vertical-align: inherit;">连接到消息代理服务器的</font></font><a href="https://www.rabbitmq.com/uri-spec.html" title="RabbitMQ URI 规范" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">AMQP URI 。</font></font></a><font style="vertical-align: inherit;"></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">AMQP_TYPE</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：消息代理类型。支持的值为</font></font><code>rabbitmq</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或</font></font><code>activemq</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。默认为</font></font><code>rabbitmq</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">REDIS_SERVER_HOST</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：运行 Redis 服务器的主机的 IP 地址或名称。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">REDIS_SERVER_PORT</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：Redis 服务器端口号。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">REDIS_SERVER_PASS</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：Redis 服务器密码。默认情况下未设置密码。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">NGINX_WORKER_PROCESSES</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义 nginx 工作进程的数量。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">NGINX_WORKER_CONNECTIONS</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：设置 nginx 工作进程可以打开的最大并发连接数。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SECURE_LINK_SECRET</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：为 nginx 配置指令</font></font><a href="https://nginx.org/en/docs/http/ngx_http_secure_link_module.html#secure_link_md5" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">secure_link_md5</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">定义秘密。默认为</font></font><code>random string</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">JWT_ENABLED</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：指定由 ONLYOFFICE 文档服务器启用 JSON Web 令牌验证。默认为</font></font><code>true</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">JWT_SECRET</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义用于验证 ONLYOFFICE 文档服务器请求中的 JSON Web 令牌的密钥。默认为随机值。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">JWT_HEADER</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义将用于发送 JSON Web 令牌的 http 标头。默认为</font></font><code>Authorization</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">JWT_IN_BODY</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：指定在 ONLYOFFICE 文档服务器的请求正文中启用令牌验证。默认为</font></font><code>false</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">WOPI_ENABLED</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：指定启用 wopi 处理程序。默认为</font></font><code>false</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ALLOW_META_IP_ADDRESS</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义是否允许连接元IP地址。默认为</font></font><code>false</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ALLOW_PRIVATE_IP_ADDRESS</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义是否允许连接私有IP地址。默认为</font></font><code>false</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">USE_UNAUTHORIZED_STORAGE</font></font></strong><font style="vertical-align: inherit;"></font><code>true</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;"> ：如果为存储服务器使用自签名证书（例如 Nextcloud），则</font><font style="vertical-align: inherit;">设置为。</font><font style="vertical-align: inherit;">默认为</font></font><code>false</code></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GENERATE_FONTS</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：当“true”时，每次开始时都会重新生成字体列表和字体缩略图等。默认为</font></font><code>true</code></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">METRICS_ENABLED</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：指定 ONLYOFFICE Document Server 的启用 StatsD。默认为</font></font><code>false</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">METRICS_HOST</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义 StatsD 侦听主机。默认为</font></font><code>localhost</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">METRICS_PORT</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义 StatsD 监听端口。默认为</font></font><code>8125</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">METRICS_PREFIX</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义后端服务的 StatsD 指标前缀。默认为</font></font><code>ds.</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">.</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LETS_ENCRYPT_DOMAIN</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义 Let's Encrypt 证书的域。</font></font></li>
<li><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">LETS_ENCRYPT_MAIL</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：定义 Let's Encrypt 证书的域管理员邮件地址。</font></font></li>
</ul>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装与社区和邮件服务器集成的 ONLYOFFICE 文档服务器</font></font></h2><a id="user-content-installing-onlyoffice-document-server-integrated-with-community-and-mail-servers" class="anchor" aria-label="永久链接：安装与社区和邮件服务器集成的 ONLYOFFICE 文档服务器" href="#installing-onlyoffice-document-server-integrated-with-community-and-mail-servers"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE文档服务器是ONLYOFFICE社区版的一部分，还包括社区服务器和邮件服务器。要安装它们，请按照以下简单步骤操作：</font></font></p>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第 1 步</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：创建</font></font><code>onlyoffice</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">网络。</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>docker network create --driver bridge onlyoffice</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="docker network create --driver bridge onlyoffice" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">然后使用“docker run --net onlyoffice”选项启动容器：</font></font></p>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第 2 步</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：安装 MySQL。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">按照</font></font><a href="#installing-mysql"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">以下步骤</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">安装 MySQL 服务器。</font></font></p>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第 3 步</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：生成 JWT 密钥</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">JWT Secret 定义密钥以验证对</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE Document Server 的</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请求中的 JSON Web 令牌。您可以自己指定它或使用以下命令轻松获取它：</font></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>JWT_SECRET=$(cat /dev/urandom | tr -dc A-Za-z0-9 | head -c 12);
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="JWT_SECRET=$(cat /dev/urandom | tr -dc A-Za-z0-9 | head -c 12);" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">步骤 4</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：安装 ONLYOFFICE 文档服务器。</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>sudo docker run --net onlyoffice -i -t -d --restart=always --name onlyoffice-document-server \
 -e JWT_ENABLED=true \
 -e JWT_SECRET=<span class="pl-smi">${JWT_SECRET}</span> \
 -e JWT_HEADER=AuthorizationJwt \
 -v /app/onlyoffice/DocumentServer/logs:/var/log/onlyoffice  \
 -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data  \
 -v /app/onlyoffice/DocumentServer/lib:/var/lib/onlyoffice \
 -v /app/onlyoffice/DocumentServer/db:/var/lib/postgresql \
 onlyoffice/documentserver</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="sudo docker run --net onlyoffice -i -t -d --restart=always --name onlyoffice-document-server \
 -e JWT_ENABLED=true \
 -e JWT_SECRET=${JWT_SECRET} \
 -e JWT_HEADER=AuthorizationJwt \
 -v /app/onlyoffice/DocumentServer/logs:/var/log/onlyoffice  \
 -v /app/onlyoffice/DocumentServer/data:/var/www/onlyoffice/Data  \
 -v /app/onlyoffice/DocumentServer/lib:/var/lib/onlyoffice \
 -v /app/onlyoffice/DocumentServer/db:/var/lib/postgresql \
 onlyoffice/documentserver" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第5步</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：安装ONLYOFFICE邮件服务器。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">为了使邮件服务器正确工作，您需要指定其主机名“yourdomain.com”。</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>sudo docker run --init --net onlyoffice --privileged -i -t -d --restart=always --name onlyoffice-mail-server -p 25:25 -p 143:143 -p 587:587 \
 -e MYSQL_SERVER=onlyoffice-mysql-server \
 -e MYSQL_SERVER_PORT=3306 \
 -e MYSQL_ROOT_USER=root \
 -e MYSQL_ROOT_PASSWD=my-secret-pw \
 -e MYSQL_SERVER_DB_NAME=onlyoffice_mailserver \
 -v /app/onlyoffice/MailServer/data:/var/vmail \
 -v /app/onlyoffice/MailServer/data/certs:/etc/pki/tls/mailserver \
 -v /app/onlyoffice/MailServer/logs:/var/log \
 -h yourdomain.com \
 onlyoffice/mailserver</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="sudo docker run --init --net onlyoffice --privileged -i -t -d --restart=always --name onlyoffice-mail-server -p 25:25 -p 143:143 -p 587:587 \
 -e MYSQL_SERVER=onlyoffice-mysql-server \
 -e MYSQL_SERVER_PORT=3306 \
 -e MYSQL_ROOT_USER=root \
 -e MYSQL_ROOT_PASSWD=my-secret-pw \
 -e MYSQL_SERVER_DB_NAME=onlyoffice_mailserver \
 -v /app/onlyoffice/MailServer/data:/var/vmail \
 -v /app/onlyoffice/MailServer/data/certs:/etc/pki/tls/mailserver \
 -v /app/onlyoffice/MailServer/logs:/var/log \
 -h yourdomain.com \
 onlyoffice/mailserver" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">邮件服务器的附加参数可</font></font><a href="https://github.com/ONLYOFFICE/Docker-CommunityServer/blob/master/docker-compose.workspace_enterprise.yml#L87"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">在此处</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">获得。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要了解更多信息，请参阅</font></font><a href="https://github.com/ONLYOFFICE/Docker-MailServer" title="ONLYOFFICE邮件服务器文档"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE 邮件服务器文档</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。</font></font></p>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">第 6 步</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：安装 ONLYOFFICE 社区服务器</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>sudo docker run --net onlyoffice -i -t -d --privileged --restart=always --name onlyoffice-community-server -p 80:80 -p 443:443 -p 5222:5222 --cgroupns=host \
 -e MYSQL_SERVER_ROOT_PASSWORD=my-secret-pw \
 -e MYSQL_SERVER_DB_NAME=onlyoffice \
 -e MYSQL_SERVER_HOST=onlyoffice-mysql-server \
 -e MYSQL_SERVER_USER=onlyoffice_user \
 -e MYSQL_SERVER_PASS=onlyoffice_pass \
 
 -e DOCUMENT_SERVER_PORT_80_TCP_ADDR=onlyoffice-document-server \
 -e DOCUMENT_SERVER_JWT_ENABLED=true \
 -e DOCUMENT_SERVER_JWT_SECRET=<span class="pl-smi">${JWT_SECRET}</span> \
 -e DOCUMENT_SERVER_JWT_HEADER=AuthorizationJwt \
 
 -e MAIL_SERVER_API_HOST=<span class="pl-smi">${MAIL_SERVER_IP}</span> \
 -e MAIL_SERVER_DB_HOST=onlyoffice-mysql-server \
 -e MAIL_SERVER_DB_NAME=onlyoffice_mailserver \
 -e MAIL_SERVER_DB_PORT=3306 \
 -e MAIL_SERVER_DB_USER=root \
 -e MAIL_SERVER_DB_PASS=my-secret-pw \
 
 -v /app/onlyoffice/CommunityServer/data:/var/www/onlyoffice/Data \
 -v /app/onlyoffice/CommunityServer/logs:/var/log/onlyoffice \
 -v /app/onlyoffice/CommunityServer/letsencrypt:/etc/letsencrypt \
 -v /sys/fs/cgroup:/sys/fs/cgroup:rw \
 onlyoffice/communityserver</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="sudo docker run --net onlyoffice -i -t -d --privileged --restart=always --name onlyoffice-community-server -p 80:80 -p 443:443 -p 5222:5222 --cgroupns=host \
 -e MYSQL_SERVER_ROOT_PASSWORD=my-secret-pw \
 -e MYSQL_SERVER_DB_NAME=onlyoffice \
 -e MYSQL_SERVER_HOST=onlyoffice-mysql-server \
 -e MYSQL_SERVER_USER=onlyoffice_user \
 -e MYSQL_SERVER_PASS=onlyoffice_pass \
 
 -e DOCUMENT_SERVER_PORT_80_TCP_ADDR=onlyoffice-document-server \
 -e DOCUMENT_SERVER_JWT_ENABLED=true \
 -e DOCUMENT_SERVER_JWT_SECRET=${JWT_SECRET} \
 -e DOCUMENT_SERVER_JWT_HEADER=AuthorizationJwt \
 
 -e MAIL_SERVER_API_HOST=${MAIL_SERVER_IP} \
 -e MAIL_SERVER_DB_HOST=onlyoffice-mysql-server \
 -e MAIL_SERVER_DB_NAME=onlyoffice_mailserver \
 -e MAIL_SERVER_DB_PORT=3306 \
 -e MAIL_SERVER_DB_USER=root \
 -e MAIL_SERVER_DB_PASS=my-secret-pw \
 
 -v /app/onlyoffice/CommunityServer/data:/var/www/onlyoffice/Data \
 -v /app/onlyoffice/CommunityServer/logs:/var/log/onlyoffice \
 -v /app/onlyoffice/CommunityServer/letsencrypt:/etc/letsencrypt \
 -v /sys/fs/cgroup:/sys/fs/cgroup:rw \
 onlyoffice/communityserver" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><strong><font style="vertical-align: inherit;">ONLYOFFICE 邮件服务器</font></strong></font><code>${MAIL_SERVER_IP}</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">的 IP 地址在</font><font style="vertical-align: inherit;">哪里</font><font style="vertical-align: inherit;">。您可以使用以下命令轻松获取它：</font></font><strong><font style="vertical-align: inherit;"></font></strong><font style="vertical-align: inherit;"></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>MAIL_SERVER_IP=$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' onlyoffice-mail-server)
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="MAIL_SERVER_IP=$(docker inspect -f '{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' onlyoffice-mail-server)" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或者，您可以使用自动安装脚本一次性安装整个 ONLYOFFICE Community Edition。为了使邮件服务器正确工作，您需要指定其主机名“yourdomain.com”。</font></font></p>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">步骤 1</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：下载社区版 Docker 脚本文件</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>wget https://download.onlyoffice.com/install/opensource-install.sh</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="wget https://download.onlyoffice.com/install/opensource-install.sh" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">步骤 2</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">：执行以下命令安装 ONLYOFFICE 社区版：</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>bash opensource-install.sh -md yourdomain.com</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="bash opensource-install.sh -md yourdomain.com" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">或者，使用</font></font><a href="https://docs.docker.com/compose/install" title="docker 撰写" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">docker-compose</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。为了使邮件服务器正确工作，您需要指定其主机名“yourdomain.com”。假设你已经安装了 docker-compose，执行以下命令：</font></font></p>
<div class="highlight highlight-source-shell notranslate position-relative overflow-auto" dir="auto"><pre>wget https://raw.githubusercontent.com/ONLYOFFICE/Docker-CommunityServer/master/docker-compose.groups.yml
docker-compose up -d</pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="wget https://raw.githubusercontent.com/ONLYOFFICE/Docker-CommunityServer/master/docker-compose.groups.yml
docker-compose up -d" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">ONLYOFFICE文档服务器ipv6设置</font></font></h2><a id="user-content-onlyoffice-document-server-ipv6-setup" class="anchor" aria-label="永久链接：ONLYOFFICE 文档服务器 ipv6 设置" href="#onlyoffice-document-server-ipv6-setup"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">（仅适用于 Linux 主机并受支持）</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Docker 目前默认不向容器提供 ipv6 地址。该功能目前处于实验阶段。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">要通过 ipv6 设置交互，您需要在 Docker 中启用对此功能的支持。为此，您需要：</font></font></p>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">创建</font></font><code>/etc/docker/daemon.json</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">包含以下内容的文件：</font></font></li>
</ul>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>{
"ipv6": true,
"fixed-cidr-v6": "2001:db8:abc1::/64"
}
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="{
&quot;ipv6&quot;: true,
&quot;fixed-cidr-v6&quot;: &quot;2001:db8:abc1::/64&quot;
}" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<ul dir="auto">
<li><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">使用以下命令重新启动 docker：</font></font><code>systemctl restart docker</code></li>
</ul>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">之后，所有正在运行的容器都会收到一个 ipv6 地址并拥有一个 inet6 接口。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">您可以检查您的默认桥接网络并查看那里的字段
</font></font><code>EnableIPv6=true</code><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">。还将添加一个新的 ipv6 子网。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">欲了解更多信息，请访问官方</font></font><a href="https://docs.docker.com/config/daemon/ipv6/" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Docker 手册网站</font></font></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">问题</font></font></h2><a id="user-content-issues" class="anchor" aria-label="永久链接：问题" href="#issues"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Docker 问题</font></font></h3><a id="user-content-docker-issues" class="anchor" aria-label="永久链接：Docker 问题" href="#docker-issues"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">作为一个相对较新的项目，Docker 正在由其社区致力于并积极开发。因此建议使用最新版本的 Docker，因为您遇到的问题可能已通过较新的 Docker 版本得到修复。</font></font></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">具有基于 rpm 的发行版的 ONLYOFFICE Document Server 的已知 Docker 问题是有时进程无法在 Docker 容器内启动。 Fedora 和 RHEL/CentOS 用户应尝试使用 setenforce 0 禁用 selinux。如果它解决了问题，那么您可以继续禁用 SELinux（RedHat 不推荐），或者改用 Ubuntu。</font></font></p>
<div class="markdown-heading" dir="auto"><h3 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">文档服务器使用问题</font></font></h3><a id="user-content-document-server-usage-issues" class="anchor" aria-label="永久链接：文档服务器使用问题" href="#document-server-usage-issues"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">由于操作特性，</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">文档服务器</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">仅在所有编辑该文档的用户关闭该文档后才保存该文档。为了避免数据丢失，</font><font style="vertical-align: inherit;">当您需要在应用程序更新、服务器重新启动等情况下停止</font><strong><font style="vertical-align: inherit;">Document Server</font></strong><font style="vertical-align: inherit;">时，必须强制断开</font></font><strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Document Server</font></font></strong><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用户的连接。 为此，请在</font><font style="vertical-align: inherit;">安装</font><strong><font style="vertical-align: inherit;">Document Server的服务器上执行以下脚本：</font></strong></font><strong><font style="vertical-align: inherit;"></font></strong><font style="vertical-align: inherit;"></font><strong><font style="vertical-align: inherit;"></font></strong><font style="vertical-align: inherit;"></font></p>
<div class="snippet-clipboard-content notranslate position-relative overflow-auto"><pre class="notranslate"><code>sudo docker exec &lt;CONTAINER&gt; documentserver-prepare4shutdown.sh
</code></pre><div class="zeroclipboard-container">
    <clipboard-copy aria-label="Copy" class="ClipboardButton btn btn-invisible js-clipboard-copy m-2 p-0 tooltipped-no-delay d-flex flex-justify-center flex-items-center" data-copy-feedback="Copied!" data-tooltip-direction="w" value="sudo docker exec <CONTAINER> documentserver-prepare4shutdown.sh" tabindex="0" role="button">
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-copy js-clipboard-copy-icon">
    <path d="M0 6.75C0 5.784.784 5 1.75 5h1.5a.75.75 0 0 1 0 1.5h-1.5a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-1.5a.75.75 0 0 1 1.5 0v1.5A1.75 1.75 0 0 1 9.25 16h-7.5A1.75 1.75 0 0 1 0 14.25Z"></path><path d="M5 1.75C5 .784 5.784 0 6.75 0h7.5C15.216 0 16 .784 16 1.75v7.5A1.75 1.75 0 0 1 14.25 11h-7.5A1.75 1.75 0 0 1 5 9.25Zm1.75-.25a.25.25 0 0 0-.25.25v7.5c0 .138.112.25.25.25h7.5a.25.25 0 0 0 .25-.25v-7.5a.25.25 0 0 0-.25-.25Z"></path>
</svg>
      <svg aria-hidden="true" height="16" viewBox="0 0 16 16" version="1.1" width="16" data-view-component="true" class="octicon octicon-check js-clipboard-check-icon color-fg-success d-none">
    <path d="M13.78 4.22a.75.75 0 0 1 0 1.06l-7.25 7.25a.75.75 0 0 1-1.06 0L2.22 9.28a.751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018L6 10.94l6.72-6.72a.75.75 0 0 1 1.06 0Z"></path>
</svg>
    </clipboard-copy>
  </div></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">请注意，执行脚本和断开用户连接可能需要很长时间（最多 5 分钟）。</font></font></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">项目信息</font></font></h2><a id="user-content-project-information" class="anchor" aria-label="永久链接：项目信息" href="#project-information"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">官方网站：</font></font><a href="https://www.onlyoffice.com/?utm_source=github&amp;utm_medium=cpc&amp;utm_campaign=GitHubDockerDS" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://www.onlyoffice.com</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">代码存储库：</font></font><a href="https://github.com/ONLYOFFICE/DocumentServer" title="https://github.com/ONLYOFFICE/DocumentServer"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://github.com/ONLYOFFICE/DocumentServer</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Docker 镜像：</font></font><a href="https://github.com/ONLYOFFICE/Docker-DocumentServer" title="https://github.com/ONLYOFFICE/Docker-DocumentServer"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://github.com/ONLYOFFICE/Docker-DocumentServer</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">许可证：</font></font><a href="https://help.onlyoffice.com/products/files/doceditor.aspx?fileid=4358397&amp;doc=K0ZUdlVuQzQ0RFhhMzhZRVN4ZFIvaHlhUjN2eS9XMXpKR1M5WEppUk1Gcz0_IjQzNTgzOTci0" title="GNU AGPL v3.0" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">GNU AGPL v3.0</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">免费版本与商业版本比较：</font></font><a href="https://github.com/ONLYOFFICE/DocumentServer#onlyoffice-document-server-editions"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://github.com/ONLYOFFICE/DocumentServer#onlyoffice-document-server-editions</font></font></a></p>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">SaaS版本：</font></font><a href="https://www.onlyoffice.com/cloud-office.aspx?utm_source=github&amp;utm_medium=cpc&amp;utm_campaign=GitHubDockerDS" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">https://www.onlyoffice.com/cloud-office.aspx</font></font></a></p>
<div class="markdown-heading" dir="auto"><h2 tabindex="-1" class="heading-element" dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">用户反馈和支持</font></font></h2><a id="user-content-user-feedback-and-support" class="anchor" aria-label="永久链接：用户反馈和支持" href="#user-feedback-and-support"><svg class="octicon octicon-link" viewBox="0 0 16 16" version="1.1" width="16" height="16" aria-hidden="true"><path d="m7.775 3.275 1.25-1.25a3.5 3.5 0 1 1 4.95 4.95l-2.5 2.5a3.5 3.5 0 0 1-4.95 0 .751.751 0 0 1 .018-1.042.751.751 0 0 1 1.042-.018 1.998 1.998 0 0 0 2.83 0l2.5-2.5a2.002 2.002 0 0 0-2.83-2.83l-1.25 1.25a.751.751 0 0 1-1.042-.018.751.751 0 0 1-.018-1.042Zm-4.69 9.64a1.998 1.998 0 0 0 2.83 0l1.25-1.25a.751.751 0 0 1 1.042.018.751.751 0 0 1 .018 1.042l-1.25 1.25a3.5 3.5 0 1 1-4.95-4.95l2.5-2.5a3.5 3.5 0 0 1 4.95 0 .751.751 0 0 1-.018 1.042.751.751 0 0 1-1.042.018 1.998 1.998 0 0 0-2.83 0l-2.5 2.5a1.998 1.998 0 0 0 0 2.83Z"></path></svg></a></div>
<p dir="auto"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">如果您对此图像有任何问题或疑问，请访问我们的官方论坛以查找问题的答案：</font></font><a href="https://forum.onlyoffice.com" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">forum.onlyoffice.com</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">，或者您可以在</font></font><a href="https://stackoverflow.com/questions/tagged/onlyoffice" rel="nofollow"><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">Stack Overflow</font></font></a><font style="vertical-align: inherit;"><font style="vertical-align: inherit;">上询问并回答 ONLYOFFICE 开发问题。</font></font></p>
</article></div>
