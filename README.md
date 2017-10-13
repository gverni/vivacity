DISCLAIMER: THIS PROJECT IS NOT ENDORSED IN ANY WAY BY VITALITY 

# Vitality chrome extension 
Chrome extension to create stats from Vitality point statement. This extension aims to use the data in the point statement to create better stats. 

# Roadmap
* Create page with weekly points (for 1+ users) 
* Create "streaks" stats 
* Autodetect of login into Vitality website
* ...

# URLs
* Log-in page: https://member.vitality.co.uk/vitality/login (or https://member.vitality.co.uk/Login when you logout)
* Landing page (after login): https://member.vitality.co.uk
:In the landing page the membership number is in ```<label id="membershipnumberlabel" class="per-info"></label>```
* Point statement page: https://member.vitality.co.uk/Vitality/MyVitality/MyPoints
* Point details: https://member.vitality.co.uk/mvc/MyPoints/GetEventListByCategory?selectedIndexValue=&month=&member=XXXXXXXXXX&year=0

# Parsing the point statement

The basic element of the poitn statement is:

```HTML
 <li data-categorylist="true" class="gray-bg padding0">
        <div class="detailed-wrp gray-point-wrp">
            <ul class="detail-wrp">
                <li class="pad14">
                    <div class="detail-one">
                        <h3 class="date">[That is the date in format dd MMM]</h3>
                    </div>
                </li>
                    <li class="MemberDetailGrid">
                        <div class="detail-two">
                            <h3 class="firstname">[Name]</h3>
                        </div>
                    </li>
                <li>
                    <div class="detail-three">
                       ( ... )
                    </div>
                </li>
                <li>
                    <div class="detail-five block-eqlheight">   
                    </div>
                </li>
                <li>
                    <div class="detail-four block-eqlheight">
                        <span data-memberpoints="true" data-memberpointsval="5" 
                              class="fields points">[This is the number of points]</span>
                    </div>
                </li>
            </ul>
        </div>
    </li>
```
