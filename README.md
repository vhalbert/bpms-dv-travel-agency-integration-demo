JBoss BPM Suite and JDV Travel Agency Integration Demo
============================================================================
This is an online employee travel booking process project. It contains multiple web services for looking up data for the process
and rules to calculate pricing. Furthermore, there are several tasks that can be activated to evaluate pricing and to review the
final booking data before completing the booking.

The backing services make use of disparate data sources integrated and exposed as services for use in this project.

Welcome to the JBoss BPM Travel Agency!


Install on your machine
----------------------------------
1. [Download and unzip.](https://github.com/eschabell/bpms-dv-travel-agency-integration-demo/archive/master.zip)

2. Add products to installs directory. For example download and add BPMS installer jar into the installs directory.

3. Run 'init.sh' or 'init.bat' file. 'init.bat' must be run with Administrative privileges.

4. Start JBoss DV Server by running 'standalone.sh  -Djboss.socket.binding.port-offset=100' or 'standalone.bat -Djboss.socket.binding.port-offset=100' in the <path-to-project>/target/dv_6.1/bin directory

5. Start JBoss BPMS Server by running 'standalone.sh' or 'standalone.bat' in the <path-to-project>/target/jboss-eap-6.4/bin directory.

6. Login to [http://localhost:8080/business-central](http://localhost:8080/business-central)

    ```
     - login for admin and other roles (u:erics / p:bpmsuite1!)
    ```
7. Create custom Dashboard entry for monitoring the external JBoss DV virtualized DB views:

    ```
    - select menus Dashboards --> Business Dashboards 

    - select Administration -->  External Connections 

    - select Create New Datasource and select radio box Custom Datasource

    - fill in form as show in screenshot:
    ```

![Datasource config](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-03.png)

    ```
    - select Check Datasource, if all goes well then Save this configuration.

    - select in Workspace pulldown menu top left the entry 'Flight and Hotel Bookings' to view virtualized tables and data.

    - monitor these when running process instances.
    ```

![Datasource tables](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-05.png)

Booking a trip 
--------------
1. Build & deploy project.

2. Start process with following data in start form (either from JBoss BPM Suite dashboard or using external client
	 UI deployed at [http://localhost:8080/external-client-ui-form-1.0](http://localhost:8080/external-client-ui-form-1.0)):

  ```
  Name: [your-name]

  Email Adress: [any-email]

  Number of Travellers: 2 

(Possible flights: Denver <--> NYC and London <--> Edinburgh)
-------------------------------------------------------------
  From Destination: London     

  To Destination: Edinburgh

  Preferred Date of Departure: 2014-12-20

  Preferred Data of Arrival: 2014-12-29

  Other Details / Notes: [any-text]
  ```

3. Login to [http://localhost:8080/business-central](http://localhost:8080/business-central)

  ```
  - login for admin role (u:erics / p:bpmsuite1!)
  ```

4. Two web services will be run and a sub-process to calculate the cost before deciding it is not needed that this booking be
	 reviewed on pricing, so you will find a task 'Employee Booking' for you to process.

5. Navigate to the "Tasks" tab and click on it. From the task in the list, click on the "Lock" icon to claim the task

6. Click on the "Work" tab from the resulting right-side pane window that opened.

7. Fill in the form provided for the task, it allows review of all the booking data submitted, generated by services and 
   calculated by the rules. You can request a review to send it back for a pricing review or check the completed box to 
   finish the task and process (isBookingConfirmed). All tasks have automated reassignment, meaning if not completed within 1 minute
   they will be put back into the group.

8. Enter credit card details (beginning with 1234...) for compensation to be triggered., Expiry details of the 
   card (e.g. 12/12) and your full name.

9. Check the logs and you will see that the process has been compensated.

10. To trigger different path for successful booking of Flights, just change the 'Credit Card details' to use any 
    card number that does not begin with 1234....

11. For details on demoing the compensation aspects of the Travel Agency demo project, 
    see [docs/compensation-howto/README-COMPENSATION.md](docs/compensation-howto/README-COMPENSATION.md)


Supporting Articles
-------------------
[Quickest Way into the Clouds with JBoss BPM Travel Agency](http://www.schabell.org/2015/02/into-clouds-with-jboss-bpm-travel-agency.html)

[Webinar - How to Excite the Travel Industry with a BPM Story](http://www.schabell.org/2015/02/webinar-how-to-excite-travel-industry.html)

[Slides from webinar - How to excite the travel industry with a BPM story](http://www.schabell.org/2015/02/slides-webinar-jboss-bpm-travel-agency.html)

[How to fly with the JBoss BPM Travel Agency (video 4 of 4)](http://www.schabell.org/2015/02/how-to-fly-with-jboss-bpm-travel-agency-part4.html)

[How to fly with the JBoss BPM Travel Agency (video 3 of 4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency-part3.html)

[How to fly with the JBoss BPM Travel Agency (video 2 of 4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency-part2.html)

[How to fly with the JBoss BPM Travel Agency (video 1 of 4)](http://www.schabell.org/2015/01/how-to-fly-with-jboss-bpm-travel-agency.html)

[Jump Start Your Rules, Events, Planning and BPM Today](http://www.schabell.org/2014/12/jump-start-rules-events-planning-bpm-today.html)

[3 Reasons You Need The New JBoss Travel Agency](http://www.schabell.org/2014/12/3-reasons-you-need-new-jboss-travel-agency.html)

[How To Excite the Travel Industry With a BPM Story](http://www.schabell.org/2014/10/how-to-excite-travel-agencies-with-bpm-story.html)


Released versions
-----------------
See the tagged releases for the following versions of the product:

- v1.0 - JBoss BPM Suite 6.1 with travel agency project using disparate data sources through JBoss DV.


![Datasource 01](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-01.png)

![Datasource 02](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-02.png)

![Datasource 03](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-03.png)

![Datasource 04](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-04.png)

![Datasource 05](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-05.png)

![Datasource 06](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-06.png)

![Datasource 07](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/datasoruce-config-07.png)

![Agency Process](https://github.com/eschabell/bpms-dv-travel-agency-integration-demo/blob/master/docs/demo-images/agency-process.png?raw=true)

![Calculate Process](https://github.com/eschabell/bpms-dv-travel-agency-integration-demo/blob/master/docs/demo-images/calculate-process.png?raw=true)

![Compensation](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/compensation-process.png?raw=true)

![Special Trips UI Form](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/SpecialTripsUIform.png)

![Started Process](https://raw.githubusercontent.com/eschabell/bpms-dv-travel-agency-integration-demo/master/docs/demo-images/started-process.png)

