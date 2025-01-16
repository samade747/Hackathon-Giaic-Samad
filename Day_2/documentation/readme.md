Home Page: A welcoming page showcasing featured products and categories with a sleek and responsive design.
Shop Page: A dedicated section to explore and filter products by categories and preferences.
Cart Page: Manage items added to the cart with real-time updates and quantity adjustments.
Order Tracking Page: Track the status and progress of ongoing orders with live updates.
Track Order Page: Users can input their order ID to find specific details about their order.
Checkout Page: A secure and smooth checkout process integrated with Stripe for payment.
Thank You Page: A confirmation page to thank users after successful order placement.





Frontend
Next.js: For building server-rendered, dynamic UIs.
Tailwind CSS: For responsive and beautiful designs.
Shadcn/UI: For customizable UI components.
Backend
Sanity CMS: To manage and structure content effectively.
Clerk: For user authentication and management.
APIs
ShipEngine API: For shipment tracking and delivery management.
Stripe API: For secure and seamless payment processing.
Tools
GitHub: For version control and collaboration.
Postman: To test and document APIs.
Vercel: For fast and reliable deployment.


Schemas
We're using Sanity CMS, so our schemas are pretty straightforward. Here's a sneak peek at our product schema:

Product
Field	Type	Description
id	String	Unique identifier for the product.
name	String	Name of the product.
price	Number	Current selling price.
stock	Number	Quantity available in stock.
description	String	Detailed description of the product.
images	Array[String]	List of image URLs for the product.
category	Reference	Associated category of the product.
createdAt	Date	Product creation date.
slug	String	URL-friendly identifier for the product.
rating	Number	Average customer rating.
originalPrice	Number	Original price before any discounts.
colors	Array[String]	Available colors for the product.
sizes	Array[String]	Available sizes for the product.
tags	Array[String]	Searchable tags associated with the product.
isNewArrival	Boolean	Flag indicating if the product is a new arrival.
isTopSelling	Boolean	Flag indicating if the product is a top-seller.
productDetails	Object	Additional details about the product.
faqs	Array[Object]	Frequently asked questions about the product.
Customer
Field	Type	Description
customerId	String	Unique identifier for the customer.
name	String	Customer's full name.
email	String	Email address of the customer.
phone	String	Contact phone number.
address	String	Residential address.
city	String	City of residence.
state	String	State of residence.
zipCode	String	ZIP or postal code.
Order
Field	Type	Description
orderId	String	Unique identifier for the order.
customer	Reference	Customer who placed the order.
items	Array[Object]	List of items in the order.
totalAmount	Number	Total cost of the order.
status	String	Current order status.
shipping	Object	Shipping details.
createdAt	Date	Order creation date.
updatedAt	Date	Last update date for the order.
Shipment
Field	Type	Description
shipmentId	String	Unique identifier for the shipment.
order	Reference	Associated order.
carrier	String	Shipping carrier name.
status	String	Current status of the shipment.
trackingId	String	Tracking ID for the shipment.
estimatedDeliveryDate	Date	Expected delivery date.
actualDeliveryDate	Date	Actual delivery date.
shippingLabel	String	URL of the shipping label.
createdAt	Date	Shipment creation date.
updatedAt	Date	Last update date for the shipment.
Category
Field	Type	Description
name	String	Name of the category.
slug	String	URL-friendly identifier.
Coupon
Field	Type	Description
code	String	Unique coupon code.
discountType	String	Type of discount (e.g., percentage, flat).
discountValue	Number	Value of the discount.
minPurchase	Number	Minimum purchase amount required.
expiryDate	Date	Expiration date of the coupon.
isActive	Boolean	Indicates if the coupon is active.