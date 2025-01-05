<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>osTicket Setup and Configuration</title>
</head>
<body>
    <h1>Help Desk Ticket Practice using open-source osTicket</h1>
    <p>
        In order to gain more hands-on skills with creating and servicing IT Help Desk tickets, I have installed and configured osTicket - an open-source (Linux Ubuntu) Help Desk ticketing software. Here is a detailed write-up of my experience with setting up, configuring, and using osTicket.
    </p>

    <h2>Prerequisites and Installation Instructions for osTicket</h2>
    <h3>Prerequisites</h3>
    <p>Ensure the following prerequisites are met before installing osTicket:</p>
    <ol>
        <li><strong>Server Requirements</strong>
            <ul>
                <li>Operating System:
                    <ul>
                        <li>Linux (recommended: Ubuntu, CentOS)</li>
                        <li>Windows (via WAMP/XAMPP)</li>
                    </ul>
                </li>
                <li>Web Server: Apache or Nginx</li>
                <li>PHP Version: 7.4 - 8.1 (as of osTicket v1.17)</li>
                <li>Database: MySQL 5.5 or later (or MariaDB equivalent)</li>
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

    <h3>Installation Instructions</h3>
    <h4>Step 1: Prepare the Server</h4>
    <ol>
        <li>Update the System:
            <pre><code>sudo apt update && sudo apt upgrade -y</code></pre>
        </li>
        <li>Install Apache, PHP, and MySQL:
            <pre><code>sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql -y</code></pre>
        </li>
        <li>Install Required PHP Extensions:
            <pre><code>sudo apt install php-mbstring php-intl php-xml php-imap php-gd php-json php-gettext php-apcu -y</code></pre>
        </li>
        <li>Secure MySQL: Run the secure installation wizard:
            <pre><code>sudo mysql_secure_installation</code></pre>
        </li>
        <li>Create a Database for osTicket:
            <pre><code>
sudo mysql -u root -p
CREATE DATABASE osticket_db;
CREATE USER 'osticket_user'@'localhost' IDENTIFIED BY 'your_password';
GRANT ALL PRIVILEGES ON osticket_db.* TO 'osticket_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;
            </code></pre>
        </li>
    </ol>

    <h4>Step 2: Download and Extract osTicket</h4>
    <ol>
        <li>Download osTicket:
            <pre><code>wget https://github.com/osTicket/osTicket/releases/download/v1.17.2/osTicket-v1.17.2.zip</code></pre>
        </li>
        <li>Extract the Package:
            <pre><code>sudo apt install unzip -y
unzip osTicket-v1.17.2.zip</code></pre>
        </li>
        <li>Move osTicket Files to the Web Root:
            <pre><code>sudo mv upload /var/www/html/osticket</code></pre>
        </li>
    </ol>

    <!-- Similar formatting continues for each step and section -->

    <h2>Post-Installation Set-Up</h2>
    <p>Here are step-by-step instructions for post-installation configuration of osTicket to ensure your system is operational and optimized:</p>
    <ol>
        <li><strong>Log in to the Admin Panel</strong>
            <ul>
                <li>Open your browser and navigate to the osTicket URL (e.g., <a href="http://yourdomain.com/scp" target="_blank">http://yourdomain.com/scp</a>).</li>
                <li>Enter the admin credentials you set during installation.</li>
            </ul>
        </li>
        <li><strong>Set Up System Preferences</strong>
            <ul>
                <li>Navigate to: Admin Panel &gt; Settings &gt; System.</li>
                <li>Configure the following:
                    <ul>
                        <li>Helpdesk Name: Enter your organization's name.</li>
                        <li>Default Email: Set the primary email address for outgoing notifications.</li>
                        <li>Helpdesk URL: Verify the base URL of your osTicket installation.</li>
                        <li>Timezone: Choose the correct timezone.</li>
                    </ul>
                </li>
                <li>Click Save Changes.</li>
            </ul>
        </li>
    </ol>

    <h2>Ticket Lifecycle Examples</h2>
    <p>Here are some ticket lifecycle examples for osTicket, demonstrating how a ticket moves through the system from creation to resolution and closure:</p>
    <ol>
        <li><strong>Example 1: IT Support Request</strong>
            <ol>
                <li>Ticket Creation</li>
                <li>Ticket Assignment</li>
                <li>Ticket Processing</li>
                <li>Ticket Resolution</li>
                <li>Ticket Closure</li>
            </ol>
        </li>
        <!-- Add more examples as needed -->
    </ol>
</body>
</html>
