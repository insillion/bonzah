|# | API | Description |
|:--:|:--:|:--|
|1|[auth](./01%20Auth.md)| Authentication request & response|
|2|[master](./02%20Masters.md)| Master request & response|
|2.1|[Premium Calculation](./02.1%20Premium%20Calculation.md)|Premium Calculation request & response|
|3|[Quote Save & Finalize](./03%20Quote%20Save_Finalize.md)| Quote Save request & response|
|4|[Payment](./04%20Payment.md)| Cash Payment request & response|
|5|[Policy](./05%20View%20Policy.md)| View Policy response|
|6|[Download PDF](./06%20Download%20PDFs.md)| Download PDF request|
|7|[Date Change Endorsement](./07%20Date%20Change%20Endorsement.md)| Modify Policy - Edit Policy Start and End Dates|
|8|[Name Change Endorsement](./08%20Name%20Change%20Endorsement.md)| Modify Policy - Edit Insured's Information|
|9|[Cancelation Endorsement](./09%20Cancelation%20Endorsement.md)| Cancel In-effect Policies|
|10|[Endorsement Payement](./10%20Endorsement%20Payment.md)| Make Payment for the Endorsement|
|11|[View Endorsement](./11%20View%20Endorsement.md)| View Endorsement|
|12|[View Pending Endorsements](./12%20View%20Pending%20Endorsements.md)| View Pending Endorsements|
|13|[List of Completed Endorsements](./13%20List%20of%20Endorsements.md)| View a list of all Completed Endorsements for a given policy|
|14|[Remove Pending Endorsement](./14%20Remove%20Pending%20Endorsement.md)| View a list of all Completed Endorsements for a given policy|


---
<br><br>
#### *Updated January 5th 2025*
<br>

# Bonzah API Requirements
## 1. API Payload Requirements
When integrating with APIs, Bonzah requires the following API connections.

<br>

<table>
  <thead>
    <tr>
      <th></th>
      <th style="width: 350px; ">Renter Data</th>
      <th style="width: 75px; "></th>
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
<br>

# 2. Website Flow Recommendations

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

<br>

---
## 3. Insurance Coverage Description
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
