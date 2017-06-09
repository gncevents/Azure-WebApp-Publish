Publishing an ASP.NET MVC 4 Application using Web Deploy

This appendix will show you how to create a new web site from the Azure Portal and publish the application you obtained by following the lab, taking advantage of the Web Deploy publishing feature provided by Azure.

<a id="ApxCTask1"></a>

<a id="Task_1_-_Creating_a_New_Web_Site_from_the_Windows_Azure_Portal"></a>
#### Task 1 - Creating a New Web Site from the Azure Portal

1. Go to the [Azure Management Portal](https://manage.windowsazure.com/) and sign in using the Microsoft credentials associated with your subscription.

    > [!NOTE]
    > With Azure you can host 10 ASP.NET Web Sites for free and then scale as your traffic grows. You can sign up [here](http://aka.ms/aspnet-hol-azure).

    ![Log on to Windows Azure portal](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image39.png "Log on to Windows Azure portal")

    *Log on to Portal*
2. Click **New** on the command bar.

    ![Creating a new Web Site](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image40.png "Creating a new Web Site")

    *Creating a new Web Site*
3. Click **Compute** | **Web Site**. Then select **Quick Create** option. Provide an available URL for the new web site and click **Create Web Site**.

    > [!NOTE]
    > Azure is the host for a web application running in the cloud that you can control and manage. The Quick Create option allows you to deploy a completed web application to the Azure from outside the portal. It does not include steps for setting up a database.

    ![Creating a new Web Site using Quick Create](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image41.png "Creating a new Web Site using Quick Create")

    *Creating a new Web Site using Quick Create*
4. Wait until the new **Web Site** is created.
5. Once the Web Site is created click the link under the **URL** column. Check that the new Web Site is working.

    ![Browsing to the new web site](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image43.png "Browsing to the new web site")

    *Browsing to the new web site*

    ![Web site running](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image43.png "Web site running")

    *Web site running*
6. Go back to the portal and click the name of the web site under the **Name** column to display the management pages.

    ![Opening the web site management pages](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image44.png "Opening the web site management pages")

    *Opening the Web Site management pages*
7. In the **Dashboard** page, under the **quick glance** section, click the **Download publish profile** link.

    > [!NOTE]
    > The *publish profile* contains all of the information required to publish a web application to a Azure for each enabled publication method. The publish profile contains the URLs, user credentials and database strings required to connect to and authenticate against each of the endpoints for which a publication method is enabled. **Microsoft WebMatrix 2**, **Microsoft Visual Studio Express for Web** and **Microsoft Visual Studio 2012** support reading publish profiles to automate configuration of these programs for publishing web applications to Azure.

    ![Downloading the web site publish profile](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image45.png "Downloading the web site publish profile")

    *Downloading the Web Site publish profile*
8. Download the publish profile file to a known location. Further in this exercise you will see how to use this file to publish a web application to Azure from Visual Studio.

    ![Saving the publish profile file](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image46.png "Saving the publish profile")

    *Saving the publish profile file*

<a id="ApxCTask2"></a>

<a id="Task_2_-_Configuring_the_Database_Server"></a>
#### Task 2 - Configuring the Database Server

If your application makes use of SQL Server databases you will need to create a SQL Database server. If you want to deploy a simple application that does not use SQL Server you might skip this task.

1. You will need a SQL Database server for storing the application database. You can view the SQL Database servers from your subscription in the Azure Management portal at **Sql Databases** | **Servers** | **Server's Dashboard**. If you do not have a server created, you can create one using the **Add** button on the command bar. Take note of the **server name and URL, administrator login name and password**, as you will use them in the next tasks. Do not create the database yet, as it will be created in a later stage.

    ![SQL Database Server Dashboard](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image47.png "SQL Database Server Dashboard")

    *SQL Database Server Dashboard*
2. In the next task you will test the database connection from Visual Studio, for that reason you need to include your local IP address in the server's list of **Allowed IP Addresses**. To do that, click **Configure**, select the IP address from **Current Client IP Address** and paste it on the **Start IP Address** and **End IP Address** text boxes and click the ![add-client-ip-address-ok-button](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image48.png) button.

    ![Adding Client IP Address](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image49.png)

    *Adding Client IP Address*
3. Once the **Client IP Address** is added to the allowed IP addresses list, click on **Save** to confirm the changes.

    ![Confirm Changes](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image50.png)

    *Confirm Changes*

<a id="ApxCTask3"></a>

<a id="Task_3_-_Publishing_an_ASPNET_MVC_4_Application_using_Web_Deploy"></a>
#### Task 3 - Publishing an ASP.NET MVC 4 Application using Web Deploy

1. Go back to the ASP.NET MVC 4 solution. In the **Solution Explorer**, right-click the web site project and select **Publish**.

    ![Publishing the Application](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image51.png "Publishing the Application")

    *Publishing the web site*
2. Import the publish profile you saved in the first task.

    ![Importing the publish profile](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image52.png "Importing the publish profile")

    *Importing publish profile*
3. Click **Validate Connection**. Once Validation is complete click **Next**.

    > [!NOTE]
    > Validation is complete once you see a green checkmark appear next to the Validate Connection button.

    ![Validating connection](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image53.png "Validating connection")

    *Validating connection*
4. In the **Settings** page, under the **Databases** section, click the button next to your database connection's textbox (i.e. **DefaultConnection**).

    ![Web deploy configuration](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image54.png "Web deploy configuration")

    *Web deploy configuration*
5. Configure the database connection as follows:

    - In the **Server name** type your SQL Database server URL using the *tcp:* prefix.
    - In **User name** type your server administrator login name.
    - In **Password** type your server administrator login password.
    - Type a new database name, for example: *MVC4SampleDB*.

    ![Configuring destination connection string](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image55.png "Configuring destination connection string")

    *Configuring destination connection string*
6. Then click **OK**. When prompted to create the database click **Yes**.

    ![Creating the database](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image56.png "Creating the database string")

    *Creating the database*
7. The connection string you will use to connect to SQL Database in Windows Azure is shown within Default Connection textbox. Then click **Next**.

    ![Connection string pointing to SQL Database](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image57.png "Connection string pointing to SQL Database")

    *Connection string pointing to SQL Database*
8. In the **Preview** page, click **Publish**.

    ![Publishing the web application](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image58.png "Publishing the web application")

    *Publishing the web application*
9. Once the publishing process finishes, your default browser will open the published web site.

    ![Application published to Windows Azure](https://github.com/aspnet/Docs/blob/master/aspnet/web-api/overview/older-versions/build-restful-apis-with-aspnet-web-api/_static/image59.png "Application published to Windows Azure")

    *Application published to Azure*
