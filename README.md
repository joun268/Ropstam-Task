# Ropstam-Task
Custom Shopify PDP with dynamic price calculator

Overview
This project implements a custom Product Detail Page (PDP) for Shopify Dawn 15.0 that calculates product prices dynamically based on Width and the corresponding Fabric Panels. The Drop option is selectable by the user, while Fabric Panels remain hidden.
The layout is 50/50: media column on the left, product options + price on the right. The price updates in real-time without page reload.
________________________________________
Features
1.	Dynamic Price Calculation
o	Based on Width selection, determine the number of Fabric Panels required.
o	Multiply Fabric Panels × Price Mapping to get the final price.
o	Price updates in real-time on the PDP.
2.	Hidden Variants
o	Fabric Panels are not shown to the user.
o	Drop is selectable and affects the product selection if needed.
o	No Shopify backend variants are required for price calculation.
3.	Add to Cart Integration
o	Uses a dummy Shopify variant (price = 0) for adding to cart.
o	Calculated price is sent as a line item property (Calculated Price) for reference in cart and order details.
4.	Responsive Layout
o	Left column: product images/videos.
o	Right column: Width, Drop, dynamic price, Add to Cart button.
o	Fully responsive for desktop and mobile.
________________________________________
Pricing Logic Explained
1.	Width → Fabric Panels
2.	{ "100": 1, "150": 2, "200": 3 }
o	Width determines how many Fabric Panels are required.
3.	Width → Price Mapping
4.	{ "100": 100, "150": 120, "200": 140 }
o	Each Fabric Panel has a price depending on Width.
5.	Final Price Calculation
6.	Final Price = Number of Fabric Panels × Price per Panel
Example:
o	Width = 150 → Panels = 2 → Price per Panel = 120
o	Final Price = 2 × 120 = 240
7.	Drop Option
o	Drop selection is visible but does not affect price in this version.
o	Can be extended to modify price if needed.
________________________________________
Limitations
•	Shopify does not allow sending dynamically calculated prices to checkout using frontend JS.
•	Calculated price is only visual on PDP and sent as a line item property.
