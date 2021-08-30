# Redemption



Placing redemption is one crucial aspect to give best customer experience to the investors. There are multiple ways you can place the redemption orders, here is a guideline on how to manage redemption orders.   


<table>
  <thead>
    <tr>
      <th style="text-align:left">Step</th>
      <th style="text-align:left">Frontend</th>
      <th style="text-align:left">Backend</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">User selects a fund to redeem</td>
      <td style="text-align:left">Total amount held in that fund to be shown.
        <br />
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">User can enter the amount that he wants to redeem</td>
      <td style="text-align:left">
        <p>Checks need to be maintained on frontend
          <br />
        </p>
        <ol>
          <li>Min redemption amount in that scheme</li>
          <li>Min redemption amount multiples.</li>
          <li>Min unit redemption</li>
          <li>Min unit redemption multiples</li>
        </ol>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">User enters whole number amount to redeem like 10k or 5k</td>
      <td style="text-align:left">Send redemption by amount to backend</td>
      <td style="text-align:left">Backend to place order of redemption by amount ( 5k or 10k)</td>
    </tr>
    <tr>
      <td style="text-align:left">User enters other than whole numbers</td>
      <td style="text-align:left">Send redemption by units.</td>
      <td style="text-align:left">Backend to place order of redemption by units.</td>
    </tr>
    <tr>
      <td style="text-align:left">USer selects entire amount</td>
      <td style="text-align:left">Send redemption by units</td>
      <td style="text-align:left">BAckend places the order of redemption of complete units held by the user.</td>
    </tr>
  </tbody>
</table>

Note

1. Do not send Close\_Ac flag as Y. This can lead to the customer getting more money than he has invested through your app as RTA will redeem the entire folio. 
2. It is always advised to give customer unit based redemption options like All units, All exit load free units etc. 
3. If user has placed a redemption request in the specific folio then those units will be blocked for redemption until either the transaction becomes success \( upon which units available will change \) or it gets failed \( upon which the units available will get refreshed\)

There are following reverse feeds from CAMS which give updates about redemption

1. WBR 33 : Normal reverse feed being received will update on the transaction processing as success or failed
2. WBR 52 : This reverse feed will tell you about the NEFT/Cheque details for the redemption that has been placed. 

Exceptions

There are few funds which have some exceptions in terms of redemptions and the same needs to be managed from backend while sending information to frontend about the redeemable untis/amount  
  


<table>
  <thead>
    <tr>
      <th style="text-align:left">Fund Type</th>
      <th style="text-align:left">Lock-in</th>
      <th style="text-align:left"></th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">ELSS</td>
      <td style="text-align:left">3 years from the date of purchase</td>
      <td style="text-align:left">
        <img src="https://lh3.googleusercontent.com/a0ymJz1C8FDCLMQLKcutIb6oerg3og3JeULOI06AqWgSFm702EZA48vzXjCQWlgoRFRcdc0wPOx-6PTyyWOdQMXeL-kDkELx4ZugHdatkiD-nVdsCARoSlCMjP1OFaUMqbC1PExj=s0"
        alt/>
      </td>
    </tr>
    <tr>
      <td style="text-align:left">Retirement Fund</td>
      <td style="text-align:left">
        <p>5 years or till retirement age (60) whichever is earlier.</p>
        <p>On completion of either, the client can choose to exit schemes.</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
    <tr>
      <td style="text-align:left">Children Fund</td>
      <td style="text-align:left">
        <p>5 years or till majority age (18) whichever is earlier.</p>
        <p>On completion of either, the client can choose to exit schemes.</p>
      </td>
      <td style="text-align:left"></td>
    </tr>
  </tbody>
</table>

