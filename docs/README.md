|# | API | Description |
|:--:|:--:|:--|
|1|[auth](./01%20Auth.md)| Authentication request & response|
|2|[master](./02%20Masters.md)| Master request & response|
|3|[Quote Save](./03%20Quote%20Save.md)| Quote Save request & response|
|4|[Quote Finalize](./04%20Quote%20Finalize.md)| Quote Finalize request & response|
|5|[Payment](./05%20Payment.md)| Cash Payment request & response|
|6|[Policy](./06%20Policy.md)| View Policy response|
|7|[Download PDF](./07%20Dowload%20PDF.md)| Download PDF request|


---
<br><br>
#### *Updated October 6th*
<br>

# Bonzah Overiew and API Requirements

### About Bonzah
Bonzah is a leading provider of car rental damage and liability insurance. Licensed in all 50 US states, Bonzah provides customers with affordable insurance options directly at the time of booking, reducing the complexity of securing coverage. Bonzah simplifies the insurance process for both travelers and car rental providers, delivering peace of mind and operational efficiency through innovative, integrated solutions.

Bonzah currently offers renters daily auto rental insurance options. We also have referral relationships with rental fleet insurers.



### Bonzah's Renter's Insurance
Auto rental insurance is personal insurance purchased as part of a rental transaction by renters of automobiles to protect rental cars and damaged third parties. These plans typically are purchased in daily or 24-hour increments and for a duration that matches the rental car contract. For example, if a rental contract is for five days, renters purchase five days of insurance.


### Fleet Insurance
Auto rental fleet insurance is commercial insurance purchased by auto rental companies to protect their fleet of cars on or near their lot and when operated by employees. These plans are typically purchased annually. Auto fleet coverage may extend to renters, but rental operators want to avoid renter claims on company insurance.

Please see our presentation for more information: [Bonzah Insurance Basics](https://docs.google.com/presentation/d/1MaHyNuGshtb5_msqjdReIbZsuQJyiihd/edit?usp=sharing&ouid=112288139653361343255&rtpof=true&sd=true)

<br><br>

---
# 1. API and Resale Requirements
When integrating with APIs, Bonzah requires the following API connections.

<br>

<table>
  <thead>
    <tr>
      <th></th>
      <th style="width: 350px;">Renter Data</th>
      <th style="width: 75px;"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Name</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Address</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Phone</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Email Address</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Date of Birth</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Driver's License Number</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Driver's License State</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>8</td>
      <td>Image of Driver's License</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>9</td>
      <td>First Licensed Date</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>10</td>
      <td>Date Issued</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>11</td>
      <td>Expiration Date</td>
      <td>If Available</td>
    </tr>
  </tbody>
</table>


<br>

<table>
  <thead>
    <tr>
      <th></th>
      <th style="width: 350px;">Rental Contract Information</th>
      <th style="width: 75px;"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Rental Start Date</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Rental End Date</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Rental Management System Booking/Reservation ID</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>4</td>
      <td>Rental Pick Up Time</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Reservation Date & Time</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Additional Driver's</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>7</td>
      <td>Rental Car Contract PDF or Image</td>
      <td>If Available</td>
    </tr>
  </tbody>
</table>


<br>


<table>
  <thead>
    <tr>
      <th></th>
      <th style="width: 350px;">Automobile Data</th>
      <th style="width: 75px;"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Year</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>2</td>
      <td>Make</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>3</td>
      <td>Model</td>
      <td>Required</td>
    </tr>
    <tr>
      <td>4</td>
      <td>VIN</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>5</td>
      <td>Rental Management System Vehicle ID</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>6</td>
      <td>Mileage Out</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>7</td>
      <td>License Plate Number</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>8</td>
      <td>License State</td>
      <td>If Available</td>
    </tr>
    <tr>
      <td>9</td>
      <td>Mileage In</td>
      <td>Optional</td>
    </tr>
  </tbody>
</table>



<br>

<table>
  <thead>
    <tr>
      <th></th>
      <th style="width: 350px;">Other</th>
      <th style="width: 75px;"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>1</td>
      <td>Rental Purchase Payment Date & Time</td>
      <td></td>
    </tr>
  </tbody>
</table>


<br><br>


---
# Website Flow Recommendations

## 1. Front Page
Bonzah is not as concerned with front page fields. In this example, the rental car company has fields for location, dates, and time.

<center><img src="/assets/1.Front page.png" alt="Sample Landing Page" width=250 ></center>

## 2. Select Auto
Bonzah suggests location, date, time, auto selection before insurance selection. This rental car company displays the available automobiles on the second page.

<center><img src="/assets/2.select auto.png" alt="Sample Landing Page" width=400></center>

## 3. Select Insurance
Bonzah recommends insurance selection as the "primary add-on" after the renter selects the automobile. This rental car company has chosen to add an insurance verification option before Bonzah insurance. 

If you or your rental car companies are looking for an insurance verification option, Bonzah has a resell agreement with one provider.

<center><img src="/assets/3. select insurance.png" alt="Sample Landing Page" width=300></center>


## 4. Select Additional Add-ons
We recommend displaying additional add-ons after insurance. Additional add-ons may include our Personal Accident/Effects Insurance (PAI), toll automation, car seats, pre-paid fuel, pet fees, to name a few.

## 5. Registration and Check-Out
Bonzah requires much of the renter's information that the RMS system will capture at the time of reservation and checkout. This information, along with some backend RMS information, will be used to create the insurance document.

## 6. Email/Notifcation
Upon the completion of payment and checkout, Bonzah will send an email to the rental customer with their insurance information. The rental car company may store the insurance documentation in its system via API. Additionally, rental car companies may access all historical Bonzah purchases and make changes to coverage on behalf of the customer via the Bonzah Business Partner Portal.

<br>

### Note:
Changes to policy duration, such as cancellation, or an extension or reduction in days, are not currently available via API. Extensions may be completed in the Bonzah Business Partner Portal by the rental car company or bonzah.com by the renter. Cancellations or reductions in policy duration may be requested in the Bonzah Business Partner Portal by using the Endorsement functionality by the rental car company or on Bonzah.com by using "_____" by the renter.

---

<br><br><br>

# Bonzah Insurance Content for Rental Company Websites
## Insurance Descriptions

Bonzah allows some liberties here, but we think the most important information to convery to rental customers is:
- Name of the policy and its acronym : E.g., "Collision Damage Waiver (CDW)"
- The italicized description.  E.g., "Covers damages to the rental vehicle when there is an accident with another vehicle."
- Values. E.g., "$35,000 in rental car coverage" or "Up to state minimum requirements for liability coverage."
- What is not covered. E.g., "Renter may still be liable for any damage done to third parties" or "Does not cover damage to the rental vehicle"

<br>

## Collision Damage Waiver (CDW) - *Rental Vehicle Protection*
Covers damages to the rental vehicle when there is an accident with another vehicle. 
- Primary insurance for accidents between vehicles. 
- Covers up to $35,000 in damage to the rental vehicle.
- Up to $500 deductible. 
- Renter may still be liable for any damage done to third parties.

<br>

## Renter's Contingent Liability Insurance (RCLI) - *Protection for Damages Done to Third Parties*
Covers 3rd parties' property and injury when renter is at fault; does not cover renter's injuries and rental vehicle.
- Primary insurance for non-rental car damages when the renter is at fault in an accident.
- Covers the legal state minimum liability requirements. Coverage amount varies based on the state.
- Bodily Injury Claims - Up to the legal state minimum requirements per person and total.
- Property Damage - Up to the legal state minimum requirements.
- Does not cover damage to the rental vehicle.

<br>

## Supplemental Liability Insurance (SLI)
Coverage is in Excess of Any Other Primary Coverage
- SLI must be used in conjunction with RCLI, a "primary insurance". SLI is not "standalone insurance".
- Secondary insurance for accidents between vehicles.
- Excess coverage up to $100,000 per person and up to $500,000 in total.
- Excess Property Damage up to $10,000 beyond any primary coverage.
- Does not cover damage to the rental vehicle.
- SLI is an optional insurance for those who want more extensive coverage.

<br>

## Personal Accident Insurance (PAI)
Covers life, medical expenses, and lost or damaged items. Personal Accident Insurance is not auto rental insurance. 
- Renter Loss of Life - $50,000
- Passenger Loss of Life - $5,000
- Accidental Medical Expense - $1,000
- Personal Effects Coverage - $500
- Does not cover damages to the rental vehicle.

<br>

## Complete Auto Guard for Renters and Additional Drivers Listed on the Rental Contract
Recommended for International Drivers and Domestic Drivers who do not own a vehicle.
Combines Primary Rental Vehicle Coverage (CDW) + 3rd Party Liability Coverage (RCLI) 

<br>

## Complete Liability Guard for Renters and Additional Drivers Listed on the Rental Contract
Combines RCLI + SLI for complete  3rd Party Liability Coverage

<br><br>

---

<br><br>

# Bonzah Branding
Bonzah suggests the folloeing messaging after the insurance descriptions.
<br>
<center><img src="/assets/bonzah logo.png" alt="Logo" width=200 style=margin-right:20px; ><img src="/assets/bonzah icon.png" alt="Logo" width=60></center>

<br><br><br>

# Bonzah Disclaimer
### The Disclaimer is most important.
You may embed this as part of your own Terms and Conditions. Locations isn’t as important to Bonzah as including it on the rental car site.

By selecting any of these insurances, the renter agrees to these [Terms and Conditions](https://bonzah.com/company/terms), [Privacy](https://bonzah.com/company/privacy), and [Covered Vehicles](https://bonzah.com/restricted-vehicle-types). Insurance is only for drivers 21 years and older with a valid driver's license. Unlicensed drivers are not entitled to coverage under any circumstances. The renter will be responsible for any unlisted additional drivers. Insurance may not apply if the renter or additional driver violates the rental agreement or violates traffic regulations. 

<br><br>

## Configuration Rewuirements and Customuzed API Usage
In addition to the requirements and guidelines above, Bonzah has additional usage requirements that you should be aware of.

<br><br>

## Supplemental Liability Insurance (SLI) Requirement 
Bonzah SLI Insurance is sold as secondary or supplemental policy, which means that it must have a primary insurance "attached" to it. Currently, we require our SLI insurance to be purchased along with our RCLI coverage. SLI cannot be purchased as a standalone policy and should be offered only with RCLI to renters. A rental car company or you may exclude to offer it all together. RCLI can be purchased as a standalone policy. This policy is in place because there is a high-level of renter intent to purchase primary liability insurance, and then they inadvertently purchase SLI only as secondary coverage.
<br><br>

## Personal Accident/Effects Insurance (PAI)
Personal Accident/Effects Insurance is not rental car coverage and is occupant injury and loss coverage for the renter and passengers in the rental car. We recommend displaying this coverage separately from our CDW, RCLI, and SLI coverages.  
<br><br>

## Vehicle Restrictions
Bonzah restricts the use of Bonzah insurance with some vehicles, typically high-end and high-performance automobiles. We will work to automate these restrictions via our APIs over time and would like to work with you on how to approach this today. Please see our site for more information.   
<br><br>

## Commercial Use Restrictions
Bonzah also restricts the use of Bonzah insurance for use with commercial vehicles. Purchase for "business travel" is ok, but things like ride share, delivery, and vehicles for hire are restricted. We are developing plans for this type of use with our insurance partners.  Please see our site for more information.
<br><br>

## Time and Date Stamping
Bonzah policy start times are based on the pickup time displayed on the rental contract. For example, if a vehicle is reserved at 12:00, has a scheduled rental start time of 2:00, and the vehicle is actually picked up at 2:30, the insurance start time is 2:30 if 2:30 is printed on the rental contract. If only the scheduled start time is printed on the rental contract, then 2:00 would be the insurance start time. To avoid any potential issues during a claim, we recommend having a date and time printed on the rental car contract. 
<br><br>

## Insurance Payments
When rental car companies are using Bonzah's APIs for embedding insurance as part of a rental reservation process, the rental car company will collect customer payments for both the auto rental and insurance purchase. At the end of the month, we will remit a bill for all insurance purchases made during the month, and rental car companies will pay us the month's outstanding balance for insurance purchases.
<br><br>

## Insurance Price Displayed
When using Bonzah APIs, please display the prices as quoted by Bonzah, unless otherwise expressly agreed to upon in writing.
<br><br>

## Custom Use of APIs
We love creativity and encourage innovative use of our APIs, such as embedding in RMS and rental car company technology. Please remember that a rental company's usage may differ from what we have conceptualized. In these unique use cases, please thoroughly test these uses before putting them into production and ask us for help with any challenges you encounter or concerns you may have.   
<br><br>

---

<br><br>

# Rental Company Onboarding
Bonzah will allow rental car companies to accept insurance payments from renters and accrue rental insurance charges during the month. We will then require the rental car company to remit insurance purchase payments to Bonzah early in the following month. For example, September insurance payments collected by rental car companies will be due in early October. Because we are extending rental car companies' credit and to establish that Pablow Inc. dba bonzah.com is the insurance agent of record, we will require all rental car customers to sign a [User Agreement](https://bonzahuseragreement.tilda.ws/). Here is the link to our rental company onboarding form: [Bonzah Business Partner Onboarding](https://www.jotform.com/form/242344002165141).
<br><br>

---
<br><br>

# Thank you!
This information is intended to help us collectively create a better experience for renters and rental car companies. For example, by having the rental contract information, we will be able to automate part of our claims process and hope to make what everyone agrees is an unpleasant experience, less unpleasant. Additionally, this data will help us to create new and better products for our partners.  

If you have any complaints, questions, or suggestions, please let us know at [brandon@bonzah.com](mailto:brandon@bonzah.com) or (515) 444-5669 (my business mobile).
