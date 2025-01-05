
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">

</head>
<body>
    <h1>Help Desk Ticket Practice using open-source osTicket</h1>
    <p>
        In order to gain more hands-on skills with creating and servicing IT Help Desk tickets, I have installed and configured osTicket - an open-source (Linux Ubuntu) Help Desk ticketing software. Here is a detailed write-up of my experience with setting up, configuring, and using osTicket.
    </p>
</body>
</html>

<h2>Step 1: Prepare the Server</h2>

<h3>Update the System:</h3>
<pre><code>sudo apt update && sudo apt upgrade -y</code></pre>

<h3>Install Apache, PHP, and MySQL:</h3>
<pre><code>sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql -y</code></pre>

<h3>Install Required PHP Extensions:</h3>
<pre><code>sudo apt install php-mbstring php-intl php-xml php-imap php-gd php-json php-gettext php-apcu -y</code></pre>

<h3>Secure MySQL: Run the secure installation wizard:</h3>
<pre><code>sudo mysql_secure_installation</code></pre>

<h3>Create a Database for osTicket:</h3>
<p>Log in to MySQL:</p>
<pre><code>sudo mysql -u root -p</code></pre>

<h2>Step 2: Download and Extract osTicket</h2>

<h3>Download osTicket:</h3>
<pre><code>wget https://github.com/osTicket/osTicket/releases/download/v1.17.2/osTicket-v1.17.2.zip</code></pre>

<h3>Extract the Package:</h3>
<pre><code>sudo apt install unzip -y

<h3>Move osTicket Files to the Web Root:</h3>
<pre><code>sudo mv upload /var/www/html/osticket</code></pre>

<h2>Step 3: Configure File Permissions</h2>

<h3>Set Permissions:</h3>
<pre><code>sudo chown -R www-data:www-data /var/www/html/osticket

<h3>Rename the Configuration File:</h3>
<p>Navigate to the osTicket directory:</p>
<pre><code>cd /var/www/html/osticket/</code></pre>

