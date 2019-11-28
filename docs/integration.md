<div class="container wrapper">
<div class="columns is-multiline">
<div class="column is-2 is-hidden-touch is-sticky is-hidden-print">
<div class="menu is-size-7">
    <ul class="menu-list"><li>
    
[Get started](integration)
</li><li>
    
[File integration](integration#csv)
</li>

<li>

</ul>
<hr class="is-smaller">
<p class="menu-label">Data sets:</p>
<ul class="menu-list"><li>

[Persons](integration#persons)
</li><li>

[Assignments](integration#assignments)
</li><li>

[Salaries](integration#salaries)
</li><li>
    
[Org Units](integration#ou)
</li><li>

[Occupations](integration#relations)
</li><li>

[Absences](integration#absences)
</li>
</ul>
</div>
    </div>
<div class="column is-10">

<h1 class="title is-1 is-family-secondary">Integrate your app with Biings</h1>

<br>

👋 Welcome to the Biings Integration documentation. If you are looking to synchronise HR data with Biings you've come to the right place.

<br>Biings has been created to work with third-party absence and time management systems as well as HRIS solutions. This documentation will help you format your data so that Biings can sychronize with your system.

<br>Before you start, [check here](apps) if the software from which your data will be exported from has a ready-made integration with Biings.

<a id="csv"></a>
<hr class="is-visible is-large">

<h1 class="title is-2">CSV file integration</h1>

Biings uses CSV files to import data from another software or database. Depending on the products enabled in your account, up to 5 sets of data (i.e. CSV files) can be synchronised with Biings. Data sets are linked to each other through Persons and Org Units IDs.

<br>The table below shows all available data sets with some being required to enable one or more Biings products.

<hr class="is-small">

| <h3 class="title is-5">Data set</h3> || Required for |
|-|-|-|
| [Persons](#persons ":target=_self")<br> | All persons/employees in your organisation with their personal details. This set should also include previous employees. | <span class="tag is-small is-info" style="background-color: #A05CB7;">Pilot</span> <span class="tag is-small is-info" style="background-color: #71C7D6;">Care</span> <span class="tag is-small is-info" style="background-color: #F89465;">Claim</span><br> |
| [ Assignements](#assignments ":target=_self") | Employees' job assignements. An assignement defines a moment in time (start and end) where the Person has worked in your organisation, where (in which Org Unit) and at what percentage (rate). A person can have more than one assignements at the same time provided that the total contract rate does not exceed 100%. | <span class="tag is-small is-info" style="background-color: #A05CB7;">Pilot</span> <span class="tag is-small is-info" style="background-color: #71C7D6;">Care</span> <span class="tag is-small is-info" style="background-color: #F89465;">Claim</span> |
| [ Salaries](#salaries ":target=_self") | Employees' salaries. A Salary record defines the salary of person for a given period of time. | <span class="tag is-small is-info" style="background-color: #F89465;">Claim</span> |
| [ Org Units](#ou ":target=_self") | All current Organisational Units (departments, services, teams, etc). This set is used to represent the organisational structure of your company. An Org Unit can be of any size or importance, either an entire department or a small team, it depends on the level of granularity you need. | <span class="tag is-small is-info" style="background-color: #A05CB7;">Pilot</span> <span class="tag is-small is-info" style="background-color: #71C7D6;">Care</span> <span class="tag is-small is-info" style="background-color: #F89465;">Claim</span> |
| [ Occupations](#relations ":target=_self") | All persons with specific occupations or management roles related to an Org. Unit. This set is used to describe the type of relation existing between employees, managers, HRBP, chiefs, etc.  | <span class="tag is-small is-info" style="background-color: #71C7D6;">Care</span> |
| [ Absences](#absences ":target=_self") | Employees' absences, including planned absences such as holidays and maternity leave. An absence is defined as a period of incapacity to work wether it is planned or unplanned. This set should include all absence history. | <span class="tag is-small is-info" style="background-color: #A05CB7;">Pilot</span> <span class="tag is-small is-info" style="background-color: #71C7D6;">Care</span> | |


<hr>

<div class="box is-raised is-popping">
    <div class="columns is-vcentered is-centered is-gapless">
        <div class="column is-2 has-text-centered"><img src="media/zip_folder.png" width="50" class="no-zoom" style="margin-right: 1rem;" class="is-pulled-left"/></div>
        <div class="column">
            <div class="title is-5">Sample CSV files</div>
            <div class="subtitle is-size-6 has-text-grey-darker">Download an example <span class="has-text-weight-semibold">pack of 5 CSV files</span>, correctly related to each other.</div>
        </div>
        <div class="column is-4 has-text-centered is-narrow">
            <br><a href="Biings_Data-set.zip" class="button is-rounded is-primary is-beefy is-glowing" style="margin-bottom: 0.25rem;">Download .zip</a>
            <div class="is-size-7 has-text-grey has-text-weight-medium">V.2.4</div>
        </div>
    </div>
</div>

<a id="csv"></a>
<hr class="is-large">

<h2 class="title is-2">Data sets</h2>
<div class="subtitle"><span class="is-size-7 has-text-grey-dark">Required fields are marked with an asterisk <code>*</code></div>
<a id="persons"></a>
</div> 

<div class="column is-2 is-hidden-print"></div>
<div class="column is-10 box is-white is-raised is-large">

<h3 class="title">Persons</h2>

<span class="is-size-7">

| Column Name | Description | Type | Format |
|-|-|-|-|
| `id` * | Unique person identifier<br><span class="has-text-orange">If `id` is empty "persons" will be ignored</span> | Int/String | |
| `lastname` * | Person's last name<br><span class="has-text-orange">If `lastname` is empty "persons" will be ignored</span>  | String ||
| `firstname` * | Person's first name<br><span class="has-text-orange">If `firstname` is empty "persons" will be ignored</span>  | String ||
| `gender` * | Gender of the person<br><span class="has-text-orange">If `gender` is empty or different than male or female "persons" will be ignored.`| String | `M` or `F` |
| `email` | Professional email address<br><span class="has-text-orange">If `email` is empty "persons" will be ignored</span>| String | abc@xyz.ch |
| `sso_account` | SSO account username | String | mdupont |
| `vacation_days` | Number of days of vacation per year, when employed at 100% | Int ||
| `phone_pro` | Professional phone number<br><span class="has-text-orange">If `phone_pro` has more than 15 characters "persons" will be ignored</span> | String | max 15 characters |
| `phone_private` | Private phone number | String | max 15 characters |
| `mobile_pro` | Professional mobile number<br><span class="has-text-orange">If `mobile_pro` has more than 15 characters "persons" will be ignored</span> | String | max 15 characters |
| `mobile_private` | Private mobile number<br><span class="has-text-orange">If `mobile_private` has more than 15 characters "persons" will be ignored</span> | String | max 15 characters |
| `address_type` | Address type | Int | `2`= Home<br>`4`= Office |
| `address_note` | Note or complement to the address | String ||
| `address_line1` | Address line 1 | String ||
| `address_line2` | Address line 2 | String ||
| `address_line3` | Address line 3 | String ||
| `address_zip` | Postal code | String ||
| `address_city` | City of residence | String ||
| `address_country` | Country code | String | ISO 3166-1 alpha-2 or alpha-3 |
| `avs_number` | Swiss AVS number | String ||
| `birthdate` | Date of birth | Int | YYYY-MM-DD |
| `start_working_date` | Date of work beginning | Int | YYYY-MM-DD |
| `marital_status` | Current marital status | Int | `1`= Single<br>`2`= Married<br>`3`= Divorced<br>`4`= Widow<br>`5`= Separated<br>`6`= Registered partnership<br>`7`= Dissolved partnership<br>`9`= Unknown_ |
| `nb_children` | Number of dependent children | Int ||
| `language` | Communication language | String | ISO 639-1 |
| `nationality` | Country code | String | ISO 3166-1 alpha-2 or alpha-3 |
| `zemis` | ZEMIS/SIMIC number<br>(for non-Swiss citizens) | String ||
| `special_cases` | Special case of insurance | Int | `0`= No particular case  <br>`1`= Family member, partner  <br>`3`= Optional insurance |
| `with_holding_tax` | Whether subjected to holding-tax from the income source | Int | `0` = No<br>`1` = Yes, is subjected to holding-tax | |


</span>
<a id="assignments"></a>
</div>

<div class="column is-2 is-hidden-print"></div>
<div class="column is-10 box is-white is-raised is-large">
    <h3 class="title">Assignements</h2>


<span class="is-size-7">

| Column Name | Description | Type | Format |
|-|-|-|-|
| `id` * | Unique Assignment identifier – recommended if available. Biings otherwise generates an Id for each unique combination of `person_id` – `start_date` – `ou_id`<br><span class="has-text-orange">If `id` is empty "Assignements" will be ignored</span>  | Int/String | |
| `person_id` * | Unique person identifier<br><span class="has-text-orange">If `person_id` is empty "Assignements" will be ignored</span>  | Int/String | |
| `ou_id` * | Org. unit identifier, matching with an `id` in the Organisational Units data set<br><span class="has-text-orange">If `ou_id` is empty "Assignements" will be ignored</span> | Any | |
| `start_date` * | Assignment start date<br><span class="has-text-orange">`start_date` must be lower than end_date or "Assignements" will be ignored</span> | String | YYYY-MM-DD |
| `end_date` *| Assignment end date<br><span class="has-text-orange">`end_date` must be greater than start_date or "Assignements" will be ignored</span>  | String, Empty or Null | YYYY-MM-DD |
| `rate` * | Rate of assignment for his/her job or particular position<br><span class="has-text-orange">`rate` must be greater than 0.01 or smaller than 1 or "Assignements" will be ignored</span> | Float | 0.0 — 1.0 |
| `contract_rate` | Main employment/contract rate.<br>In most situations, a person is hired to fill one position. In that case the contract_rate and assignment have the same rate. When an employee fills more than one position (aka assignments), the sum of all assignment rates equals the overall contract rate<br><span class="has-text-orange">`contract_rate` must be greater than 0.01 or smaller than 1 or "Assignements" will be ignored</span> | Float | 0.0 — 1.0 |
| `job_id` * | Unique job/position identifier<br><span class="has-text-orange">If `job_id` is empty "Assignements" will be ignored</span> | Int | |
| `job_function` | Job/position function or profession | String | Project manager, Nurse,..  |
| `job_custom_filter1` | Job/position custom key filter 1 | String | |
| `job_custom_filter2` | Job/position custom key filter 2| String | |
| `job_custom_filter3` | Job/position custom key filter 3 | String | |
| `weekly_hours` | Working hours per week | Float | |

</span>

<a id="salaries"></a>
</div>

<div  class="column is-2 is-hidden-print"></div>
<div class="column is-10 box is-white is-raised is-large">
    <h3 class="title">Salaries</h2>

<span class="is-size-7">

?> Please include salaries code `101`, `102` and `103` in case they are different than the Person's main basic salary (`100`).

<br>

| Column Name | Description | Type | Format |
|-|-|-|-|
| `person_id` * | Person ID, matching with a `person_id` in the Person data set.| Int | <img width="200"/> |
| `code` * | Type of salary or type of benefits. | Int | `100` = basic salary (gross salary)<br>`200` = childs and family benefits<br>`300` = free (bonus, 13th salary,...)<br>`400` = vacation and public holiday compensation<br>`500` = other supplements<br>`101` = basic salary (gross salary) for LAA<br>`102` = basic salary (gross salary) for LAAC<br>`103` = basic salary (gross salary) for PGM |
| `amount` * | Salary amount | Float | |
| `period` * | Period at which the salary is paid. | Int | `1` = hourly<br>`2` = daily<br>`3` = monthly<br>`4` = yearly<br>`5` = one time |
| `start_date`* | Date at which the salary starts to be effective. | Date | |
| `end_date`* | Date at which the salary stops being effective. | Date | |
| `currency` | Currency used for the salary. | Char(3) | |

</span>

<a id="ou"></a>
</div>

<div class="column is-2 is-hidden-print"></div>
<div class="column is-10 box is-white is-raised is-large">
    <h3 class="title">Organisational Units</h2>

<span class="is-size-7">

!> This set should include <u>ONLY</u> current Org Units (history should not be included).

| Column Name | Description | Type | Format |
|-|-|-|-|
| `id` * | Unique unit identifier<br><span class="has-text-orange">If `id` is empty "Organisational Units" will be ignored</span> | Int/String | |
| `parent_id` * | Parent Unit identifier<br><span class="has-text-orange">If `parent_id` is empty "Organisational Units" will be ignored</span> | Int/String ||
| `name` * | Unit name<br><span class="has-text-orange">If `name` is empty "Organisational Units" will be ignored</span> | String | Human resource, finance,.. |


</span>
<a id="relations"></a>
</div>

<div  class="column is-2 is-hidden-print"></div>
<div class="column is-10 box is-white is-raised is-large">
    <h3 class="title">Occupations</h2>

<span class="is-size-7">

| Column Name | Description | Type | Format |
|-|-|-|-|
| `person_id` * | Person ID, matching with a `person_id` in the Person data set<br><span class="has-text-orange">If `person_id` is empty "Occupations" will be ignored</span> | Int/String | |
| `to_person_id` * | The Person ID towards who the relation is<br><span class="has-text-orange">If `to_person_id` is empty "Occupations" will be ignored</span> | Int/String | |
| `kind` * | Kind of relation<br><span class="has-text-orange">If `kind` is empty "Occupations" will be ignored</span> | Int | `1`= Substitute manager<br>`2`= Manager<br>`4`= RH |

</span>
<a id="absences"></a>
</div>

<div class="column is-2 is-hidden-print"></div>
<div class="column is-10 box is-white is-raised is-large">
    <h3 class="title">Absences</h2>

<span class="is-size-7">

?> Biings applies [automatic linking rules](autolinking) when syncing with external absence database.

<br>

| Column Name | Description | Type | Format |
|:-|:-|:-:|:-|
| `id` * | Unique absence identifier<br>(Can be omitted for a single data import)<br><span class="has-text-orange">If `id` is empty "Absences" will be ignored</span> | Int/String | |
| `person_id` * | Absent identifier, matching with `person_id` in the collaborator data set<br><span class="has-text-orange">If `person_id` is empty "Absences" will be ignored</span>  | | |
| `case_id` | Case identifier, grouping multiple absence together | Int ||
| `from` * | Date at which the work incapacity started<br>Time values are optional.<br><span class="has-text-orange">`from` mustn't be empty or upper than end_date, in that case "Absences" will be ignored</span> | String | YYYY-MM-DD<br>hh:mm |
| `until` * | Date at which the work incapacity ended<br>Null or Empty means the absence is still in progress<br><span class="has-text-orange">`until` mustn't be empty or lower than start_date, in that case "Absences" will be ignored</span> | String, Null or Empty| YYYY-MM-DD<br>hh:mm |
| `time_due` | Minutes of work due (or missed) during the absence<br>When_ `time_due` _is given, it acts as a replacement to the calendar duration (i.e. `until` / `from`) when computing the general absence rate. <br><span class="has-text-orange">All computing rules and rates should be already applied. Biings will not apply any treatment to it and use the value as is.</span>| Int | 120 |
| `rate` * | Work incapacity rate.<br>100% means completly absent.<br><span class="has-text-orange">`rate` must be greater than 0.01 or smaller than 1 or "Absences" will be ignored</span> | Float | 0.0 to 1.0 |
| `reason_id` | Reason or Cause code/identifier. | String or Int | |
| `reason` * | Absence reason/cause label<br><span class="has-text-orange"></span>If `reason` is empty "Absences" will be ignored</span> | String | `illness`<br>`accident`<br>`maternity`<br>`maternity`<br>`holiday`<br>`service`<br>`rest`<br>`special` |
| `planned` | Whether the absence is planned or not | Int | `0`= unplanned<br>`1`= planned |
| `comment` | Any notes available about that particular absence | String | Prefers to be contacted on his mobile phone. |

</span>
</div>

</div>
</div>
