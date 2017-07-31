# scala-capstone
knolkart.com is a new online shopping application with microservices architecture. Inventory is one of the service which needs to be accessed from several other services. Therefore in order to reduce the code duplicacy and easeness in accessing inventory, the team has decided to create an sdk as a separate module so that other services like checkout-service and notification-service can use it as a tool.  Access point of inventory could be anything like rest endpoint, Kafka topic or any socket connection. In order to implement the SDK following stories need to be implemented. Make sure you break all the stories to different engineering tasks. Create necessary case classes and use appropriate collection for them, use all necessary Scala features to build the module.  Each stories need to fulfill the following definition of done.

1. Self code review
2. 95% unit test coverage
3. 0 scalastyle
4. All features must be in runnable condition.
5. Flow class/diagram updated in wiki
6. How to run updated in wiki.
<p>
1. As an architect, I would like to setup a multi module project using sbt <br>
 <AC>
 <ul>
  <li>a. Have modules inventory, inventory-sdk, checkout-service, notification-service</li>
  <li>b. Have proper package structure.</li>
 </ul>
</p>
<p>
2. As an architect, I would like to access inventory to show search items so that it can be shown in UI or access by analytics.
Acceptance criteria
 <ul>
  <li>a. List of items with details like description, photos,  vendor information, price.</li>
  <li>b.Takes category, item name and some filter parameter like default, price low to high, price high to low</li>
  <li>c. If filter is not default it must sort them using price.</li>
  <li>d. Returns in a Future.</li>
  <li>e. Accepts the credentials in Map form implicitly.</li>
 </ul>
</p>
<p>
3. As an architect, I would like to access inventory to get the price info so that it can be use in checkout service or in notification service<br>
AC
 <ul>
 <li>a. Accepts item id to get the price information</li>
 <li>b. Returns the price object</li>
 <li>c. Returns in a Future</li>
 <li>d. Accepts the credentials in Map form implicitly.</li>
 </ul>
</p>
<p>
4. As an architect, I would like to use the inventory item and can update the item count. .<br>
AC
 <ul>
  <li>a. Accepts item id and number to be reduced.</li>
  <li> b. Returns if it is updated.</li>
  <li> c. It must be a higher order function  e.g. checkout(id: Long, itemCount: Int)(A => B)</li>
  <li> d returns in a Future</li>
  <li> e Accepts the credentials in Map form implicitly.</li>
  </ul>
</p>
<p>
5. As an architect, I would like add items to inventory from backend service. <br>
 AC
 <ul>
  <li>a. Accepts item information along with number of items available</li>
  <li> b. Returns its id. </li>
  <li> c. Returns in a Future </li>
  <li> d. Accepts the credentials in Map form implicitly. </li>
  </ul>
</p>
