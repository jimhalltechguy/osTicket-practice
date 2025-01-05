<hr>

<h2>Prerequisites and Installation Instructions for osTicket</h2>

<h3>Prerequisites</h3>
<p>Ensure the following prerequisites are met before installing osTicket:</p>
<ol>
    <li><strong>Server Requirements</strong>
        <ul>
            <li><strong>Operating System:</strong>
                <ul>
                    <li>Linux (recommended: Ubuntu, CentOS)</li>
                    <li>Windows (via WAMP/XAMPP)</li>
                </ul>
            </li>
            <li><strong>Web Server:</strong> Apache or Nginx</li>
            <li><strong>PHP Version:</strong> 7.4 - 8.1 (as of osTicket v1.17)</li>
            <li><strong>Database:</strong> MySQL 5.5 or later (or MariaDB equivalent)</li>
        </ul>
    </li>
    <li><strong>PHP Extensions</strong>
        <ul>
            <li>mysqli</li>
            <li>gd</li>
            <li>gettext</li>
            <li>imap</li>
            <li>mbstring</li>
            <li>xml</li>
            <li>intl</li>
            <li>fileinfo</li>
            <li>json</li>
            <li>phar</li>
            <li>apcu (optional but recommended for caching)</li>
        </ul>
    </li>
    <li><strong>Tools and Packages</strong>
        <ul>
            <li>SSH or terminal access (for server setup)</li>
            <li>FTP client (e.g., FileZilla) or SCP for file uploads</li>
            <li>Text editor (e.g., VSCode or Notepad++)</li>
            <li>A domain or subdomain with DNS configured to point to your server</li>
        </ul>
    </li>
    <li><strong>osTicket Installation Package</strong>
        <ul>
            <li>Download the latest osTicket package from the official osTicket website.</li>
        </ul>
    </li>
</ol>

<hr>

<h3>Installation Instructions</h3>

<h4>Step 1: Prepare the Server</h4>
<ol>
    <li><strong>Update the System:</strong>
        <pre><code>sudo apt update && sudo apt upgrade -y</code></pre>
    </li>
    <li><strong>Install Apache, PHP, and MySQL:</strong>
        <pre><code>sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql -y</code></pre>
    </li>
    <li><strong>Install Required PHP Extensions:</strong>
        <pre><code>sudo apt install php-mbstring php-intl php-xml php-imap php-gd php-json php-gettext php-apcu -y</code></pre>
    </li>
    <li><strong>Secure MySQL:</strong> Run the secure installation wizard:
        <pre><code>sudo mysql_secure_installation</code></pre>
    </li>
    <li><strong>Create a Database for osTicket:</strong>
        <pre><code>
<h4>Step 2: Download and Extract osTicket</h4>
<ol>
    <li><strong>Download osTicket:</strong>
        <pre><code>wget https://github.com/osTicket/osTicket/releases/download/v1.17.2/osTicket-v1.17.2.zip</code></pre>
    </li>
    <li><strong>Extract the Package:</strong>
        <pre><code>sudo apt install unzip -y
<h4>Step 3: Configure File Permissions</h4>
<ol>
    <li><strong>Set Permissions:</strong>
        <pre><code>sudo chown -R www-data:www-data /var/www/html/osticket
<h4>Step 4: Configure Apache</h4>
<ol>
    <li><strong>Create a Virtual Host Configuration:</strong>
        <pre><code>
