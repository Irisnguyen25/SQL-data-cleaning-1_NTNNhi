# SQL-data-cleaning-1_NTNNhi
## Introduction
This is an educational project on data cleaning and preparation using SQL. The original database in CSV format is located in the file club_member_info.csv. Here, we will explore the steps that need to be applied to obtain a cleansed version of the dataset.
## Part 2: Prepare an SQLLite database to work
### Get the 10 first rows from the table using SQL console

SELECT * FROM club_member_info cmi LIMIT 10;

|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|
|addie lush|40|married|alush0@shutterfly.com|254-389-8708|3226 Eastlawn Pass,Temple,Texas|Assistant Professor|7/31/2013|
|      ROCK CRADICK|46|married|rcradick1@newsvine.com|910-566-2007|4 Harbort Avenue,Fayetteville,North Carolina|Programmer III|5/27/2018|
|Sydel Sharvell|46|divorced|ssharvell2@amazon.co.jp|702-187-8715|4 School Place,Las Vegas,Nevada|Budget/Accounting Analyst I|10/6/2017|
|Constantin de la cruz|35||co3@bloglines.com|402-688-7162|6 Monument Crossing,Omaha,Nebraska|Desktop Support Technician|10/20/2015|
|  Gaylor Redhole|38|married|gredhole4@japanpost.jp|917-394-6001|88 Cherokee Pass,New York City,New York|Legal Assistant|5/29/2019|
|Wanda del mar       |44|single|wkunzel5@slideshare.net|937-467-6942|10864 Buhler Plaza,Hamilton,Ohio|Human Resources Assistant IV|3/24/2015|
|Joann Kenealy|41|married|jkenealy6@bloomberg.com|513-726-9885|733 Hagan Parkway,Cincinnati,Ohio|Accountant IV|4/17/2013|
|   Joete Cudiff|51|divorced|jcudiff7@ycombinator.com|616-617-0965|975 Dwight Plaza,Grand Rapids,Michigan|Research Nurse|11/16/2014|
|mendie alexandrescu|46|single|malexandrescu8@state.gov|504-918-4753|34 Delladonna Terrace,New Orleans,Louisiana|Systems Administrator III|3/12/1921|
| fey kloss|52|married|fkloss9@godaddy.com|808-177-0318|8976 Jackson Park,Honolulu,Hawaii|Chemical Engineer|11/5/2014|

## Part 3: Cleaning and Documentating
### Make a copy of table
CREATE TABLE club_member_info_cleaned (full_name VARCHAR(50),age INTEGER,martial_status VARCHAR(50),email VARCHAR(50),phone VARCHAR(50),full_address VARCHAR(50),
	job_title VARCHAR(50),membership_date VARCHAR(50));
INSERT INTO club_member_info_cleaned 
Select * from club_member_info;
SELECT * FROM club_member_info_cleaned cmic LIMIT 10;

|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|
|addie lush|40|married|alush0@shutterfly.com|254-389-8708|3226 Eastlawn Pass,Temple,Texas|Assistant Professor|7/31/2013|
|      ROCK CRADICK|46|married|rcradick1@newsvine.com|910-566-2007|4 Harbort Avenue,Fayetteville,North Carolina|Programmer III|5/27/2018|
|Sydel Sharvell|46|divorced|ssharvell2@amazon.co.jp|702-187-8715|4 School Place,Las Vegas,Nevada|Budget/Accounting Analyst I|10/6/2017|
|Constantin de la cruz|35||co3@bloglines.com|402-688-7162|6 Monument Crossing,Omaha,Nebraska|Desktop Support Technician|10/20/2015|
|  Gaylor Redhole|38|married|gredhole4@japanpost.jp|917-394-6001|88 Cherokee Pass,New York City,New York|Legal Assistant|5/29/2019|
|Wanda del mar       |44|single|wkunzel5@slideshare.net|937-467-6942|10864 Buhler Plaza,Hamilton,Ohio|Human Resources Assistant IV|3/24/2015|
|Joann Kenealy|41|married|jkenealy6@bloomberg.com|513-726-9885|733 Hagan Parkway,Cincinnati,Ohio|Accountant IV|4/17/2013|
|   Joete Cudiff|51|divorced|jcudiff7@ycombinator.com|616-617-0965|975 Dwight Plaza,Grand Rapids,Michigan|Research Nurse|11/16/2014|
|mendie alexandrescu|46|single|malexandrescu8@state.gov|504-918-4753|34 Delladonna Terrace,New Orleans,Louisiana|Systems Administrator III|3/12/1921|
| fey kloss|52|married|fkloss9@godaddy.com|808-177-0318|8976 Jackson Park,Honolulu,Hawaii|Chemical Engineer|11/5/2014|

### Clean data and document it
#### UPPER letter in Full name
UPDATE club_member_info_cleaned SET full_name = UPPER(full_name);
SELECT * from club_member_info_cleaned cmic LIMIT 10;

|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|
|ADDIE LUSH|40|married|alush0@shutterfly.com|254-389-8708|3226 Eastlawn Pass,Temple,Texas|Assistant Professor|7/31/2013|
|      ROCK CRADICK|46|married|rcradick1@newsvine.com|910-566-2007|4 Harbort Avenue,Fayetteville,North Carolina|Programmer III|5/27/2018|
|SYDEL SHARVELL|46|divorced|ssharvell2@amazon.co.jp|702-187-8715|4 School Place,Las Vegas,Nevada|Budget/Accounting Analyst I|10/6/2017|
|CONSTANTIN DE LA CRUZ|35||co3@bloglines.com|402-688-7162|6 Monument Crossing,Omaha,Nebraska|Desktop Support Technician|10/20/2015|
|  GAYLOR REDHOLE|38|married|gredhole4@japanpost.jp|917-394-6001|88 Cherokee Pass,New York City,New York|Legal Assistant|5/29/2019|
|WANDA DEL MAR       |44|single|wkunzel5@slideshare.net|937-467-6942|10864 Buhler Plaza,Hamilton,Ohio|Human Resources Assistant IV|3/24/2015|
|JOANN KENEALY|41|married|jkenealy6@bloomberg.com|513-726-9885|733 Hagan Parkway,Cincinnati,Ohio|Accountant IV|4/17/2013|
|   JOETE CUDIFF|51|divorced|jcudiff7@ycombinator.com|616-617-0965|975 Dwight Plaza,Grand Rapids,Michigan|Research Nurse|11/16/2014|
|MENDIE ALEXANDRESCU|46|single|malexandrescu8@state.gov|504-918-4753|34 Delladonna Terrace,New Orleans,Louisiana|Systems Administrator III|3/12/1921|
| FEY KLOSS|52|married|fkloss9@godaddy.com|808-177-0318|8976 Jackson Park,Honolulu,Hawaii|Chemical Engineer|11/5/2014|

#### Remove leading and trailing space in full_name column
UPDATE club_member_info_cleaned set full_name =TRIM(full_name);
SELECT * from club_member_info_cleaned cmic LIMIT 20;

|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|
|ADDIE LUSH|40|married|alush0@shutterfly.com|254-389-8708|3226 Eastlawn Pass,Temple,Texas|Assistant Professor|7/31/2013|
|ROCK CRADICK|46|married|rcradick1@newsvine.com|910-566-2007|4 Harbort Avenue,Fayetteville,North Carolina|Programmer III|5/27/2018|
|SYDEL SHARVELL|46|divorced|ssharvell2@amazon.co.jp|702-187-8715|4 School Place,Las Vegas,Nevada|Budget/Accounting Analyst I|10/6/2017|
|CONSTANTIN DE LA CRUZ|35||co3@bloglines.com|402-688-7162|6 Monument Crossing,Omaha,Nebraska|Desktop Support Technician|10/20/2015|
|GAYLOR REDHOLE|38|married|gredhole4@japanpost.jp|917-394-6001|88 Cherokee Pass,New York City,New York|Legal Assistant|5/29/2019|
|WANDA DEL MAR|44|single|wkunzel5@slideshare.net|937-467-6942|10864 Buhler Plaza,Hamilton,Ohio|Human Resources Assistant IV|3/24/2015|
|JOANN KENEALY|41|married|jkenealy6@bloomberg.com|513-726-9885|733 Hagan Parkway,Cincinnati,Ohio|Accountant IV|4/17/2013|
|JOETE CUDIFF|51|divorced|jcudiff7@ycombinator.com|616-617-0965|975 Dwight Plaza,Grand Rapids,Michigan|Research Nurse|11/16/2014|
|MENDIE ALEXANDRESCU|46|single|malexandrescu8@state.gov|504-918-4753|34 Delladonna Terrace,New Orleans,Louisiana|Systems Administrator III|3/12/1921|
|FEY KLOSS|52|married|fkloss9@godaddy.com|808-177-0318|8976 Jackson Park,Honolulu,Hawaii|Chemical Engineer|11/5/2014|
|DARWIN VENTAM|42|married|dventama@uol.com.br|203-993-0118|2254 Express Hill,New Haven,Connecticut|Chemical Engineer|3/12/2017|
|MOHANDAS PEEVER|38|single|mpeeverb@ed.gov|805-968-3034|0 Lukken Plaza,Bakersfield,California|Programmer I|8/1/2015|
|MANDIE OLWEN|29|single|molwenc@phoca.cz|612-914-2658|61 Blue Bill Park Plaza,Minneapolis,Minnesota|Business Systems Development Analyst|6/16/2019|
|EVANIA CADWALADR|32|single|ecadwaladrd@patch.com|702-364-0009|98965 Riverside Terrace,Santa Barbara,California|Accounting Assistant I|3/18/2017|
|KARLENE O'MAILEY|48|single|komaileye@ftc.gov|608-659-4566|45583 Spenser Junction,Madison,Wisconsin|Programmer II|7/16/2021|
|ANNAMARIA CROSSGROVE|55|married|acrossgrovef@amazon.com|818-861-1707|487 Buell Lane,Glendale,California|Tax Accountant|7/10/2018|
|HORTEN PEASNONE|47|divorced|hpeasnoneg@indiegogo.com|405-571-6677|7 Hansons Trail,Oklahoma City,Oklahoma|Quality Control Specialist|6/10/2019|
|KERR DORKIN|41|divorced|kdorkinh@admin.ch|702-560-2980|75 Basil Terrace,Las Vegas,Nevada|Senior Financial Analyst|5/16/2021|
|ED HAMBRIBE|38|divorced|ehambribei@china.com.cn|770-167-4852|04354 Graceland Junction,Marietta,Georgia|Community Outreach Specialist|6/18/2014|
|GEOFFRY BOUETTE|33|married|gbouettej@live.com|361-160-6496|53 Knutson Way,Corpus Christi,Texas|Systems Administrator I|11/19/2014|

#### Determine Ages which are out of realistic range (Range: 18<= age <= 90)
SELECT * from club_member_info_cleaned cmic where age < 18 or age >90 or age is NULL;

|full_name|age|martial_status|email|phone|full_address|job_title|membership_date|
|---------|---|--------------|-----|-----|------------|---------|---------------|
|JORI SANZ|399|married|jsanz3i@google.cn|904-906-7537|99 West Crossing,Jacksonville,Florida|Professor|2/15/2012|
|CARLYE GRAEBER|555|married|cgraeber6n@quantcast.com|214-345-1363|8 Dexter Junction,Dallas,Texas|Actuary|3/10/2021|
|SHURWOOD STRUTLEY|544|married|sstrutley9w@craigslist.org|804-636-0234|7779 Main Road,Richmond,Virginia|Nuclear Power Engineer|6/30/2014|
|CORBIN HILLAN|499|single|chillandg@time.com|267-229-4017|78 La Follette Trail,Philadelphia,Pennsylvania|Account Representative II|7/7/2021|
|SMITTY BULMER|522|divorced|sbulmergm@addthis.com||23370 Forest Dale Street,Pittsburgh,Pennsylvania|VP Marketing|9/25/2017|
|LEONORE BOOTHJARVIS||married|lboothjarvisi2@bloglines.com|713-618-0516|33110 Luster Plaza,Houston,Texas|Sales Representative|6/13/2022|
|AUNDREA VILLAR|277|married|avillarm8@privacy.gov.au|571-942-0462|58201 Utah Terrace,Arlington,Virginia|Senior Sales Associate|6/28/2012|
|CHERY BATISSE||divorced|cbatissen3@bandcamp.com|804-431-7226|604 Elgar Way,Richmond,Virginia|VP Product Management|7/30/2012|
|ERINA AUBERT|288|married|eaubertqp@cargocollective.com|615-711-2470|2597 Hallows Road,Nashville,Tennessee|Automation Specialist II|11/2/2012|
|BALDWIN RIPPEN|588|single|brippen1z@nationalgeographic.com|912-469-5562|2 Esker Alley,Savannah,Georgia|Web Developer II|12/1/2015|
|CHERISE KRISTOFFERSSON|599|divorced|ckristoffersson59@sun.com|806-779-9348|72793 Northridge Park,Lubbock,Texas|Director of Sales|8/2/2021|
|THORNDIKE PORTINGALE|677|married|tportingale9n@nsw.gov.au|941-186-3805|9011 Huxley Plaza,Sarasota,Florida|Statistician II|2/16/2019|
|HASKELL BRADEN|322|divorced|hbradenri@freewebs.com|510-963-9848|35005 Waubesa Crossing,Berkeley,California|Dental Hygienist|11/4/2015|
|MONTAGUE LATHAM|644|married|mlathame5@dailymotion.com|210-522-8041|0 Buhler Plaza,San Antonio,Texas|Administrative Officer|2/13/2021|
|VIRGINA HUBBOCK||single|vhubbockep@ed.gov|540-535-0069|7 Schmedeman Center,Roanoke,Virginia|Media Manager I|7/6/2021|
|ALVA DELL 'ORTO|411|married|adellhp@yale.edu|951-142-9340|10 Carpenter Lane,Riverside,California|Food Chemist|3/10/2019|
|DENNI STALLARD|633|single|dstallardl9@devhub.com|816-567-5883|73737 Kinsman Street,Saint Joseph,Missouri|Nuclear Power Engineer|7/3/2018|
|CATHRINE JONSON|222|married|cjonsonol@aboutads.info|559-318-4841|4147 Swallow Hill,Fresno,California|Speech Pathologist|4/26/2022|
|JORI SANZ|399|married|jsanz3i@google.cn|904-906-7537|99 West Crossing,Jacksonville,Florida|Professor|2/15/2012|
|CARLYE GRAEBER|555|married|cgraeber6n@quantcast.com|214-345-1363|8 Dexter Junction,Dallas,Texas|Actuary|3/10/2021|
|SHURWOOD STRUTLEY|544|married|sstrutley9w@craigslist.org|804-636-0234|7779 Main Road,Richmond,Virginia|Nuclear Power Engineer|6/30/2014|
|CORBIN HILLAN|499|single|chillandg@time.com|267-229-4017|78 La Follette Trail,Philadelphia,Pennsylvania|Account Representative II|7/7/2021|
|SMITTY BULMER|522|divorced|sbulmergm@addthis.com||23370 Forest Dale Street,Pittsburgh,Pennsylvania|VP Marketing|9/25/2017|
|LEONORE BOOTHJARVIS||married|lboothjarvisi2@bloglines.com|713-618-0516|33110 Luster Plaza,Houston,Texas|Sales Representative|6/13/2022|
|AUNDREA VILLAR|277|married|avillarm8@privacy.gov.au|571-942-0462|58201 Utah Terrace,Arlington,Virginia|Senior Sales Associate|6/28/2012|
|CHERY BATISSE||divorced|cbatissen3@bandcamp.com|804-431-7226|604 Elgar Way,Richmond,Virginia|VP Product Management|7/30/2012|
|ERINA AUBERT|288|married|eaubertqp@cargocollective.com|615-711-2470|2597 Hallows Road,Nashville,Tennessee|Automation Specialist II|11/2/2012|
|BALDWIN RIPPEN|588|single|brippen1z@nationalgeographic.com|912-469-5562|2 Esker Alley,Savannah,Georgia|Web Developer II|12/1/2015|
|CHERISE KRISTOFFERSSON|599|divorced|ckristoffersson59@sun.com|806-779-9348|72793 Northridge Park,Lubbock,Texas|Director of Sales|8/2/2021|
|THORNDIKE PORTINGALE|677|married|tportingale9n@nsw.gov.au|941-186-3805|9011 Huxley Plaza,Sarasota,Florida|Statistician II|2/16/2019|
|HASKELL BRADEN|322|divorced|hbradenri@freewebs.com|510-963-9848|35005 Waubesa Crossing,Berkeley,California|Dental Hygienist|11/4/2015|
|MONTAGUE LATHAM|644|married|mlathame5@dailymotion.com|210-522-8041|0 Buhler Plaza,San Antonio,Texas|Administrative Officer|2/13/2021|
|VIRGINA HUBBOCK||single|vhubbockep@ed.gov|540-535-0069|7 Schmedeman Center,Roanoke,Virginia|Media Manager I|7/6/2021|
|ALVA DELL 'ORTO|411|married|adellhp@yale.edu|951-142-9340|10 Carpenter Lane,Riverside,California|Food Chemist|3/10/2019|
|DENNI STALLARD|633|single|dstallardl9@devhub.com|816-567-5883|73737 Kinsman Street,Saint Joseph,Missouri|Nuclear Power Engineer|7/3/2018|
|CATHRINE JONSON|222|married|cjonsonol@aboutads.info|559-318-4841|4147 Swallow Hill,Fresno,California|Speech Pathologist|4/26/2022|
|JORI SANZ|399|married|jsanz3i@google.cn|904-906-7537|99 West Crossing,Jacksonville,Florida|Professor|2/15/2012|
|CARLYE GRAEBER|555|married|cgraeber6n@quantcast.com|214-345-1363|8 Dexter Junction,Dallas,Texas|Actuary|3/10/2021|
|SHURWOOD STRUTLEY|544|married|sstrutley9w@craigslist.org|804-636-0234|7779 Main Road,Richmond,Virginia|Nuclear Power Engineer|6/30/2014|
|CORBIN HILLAN|499|single|chillandg@time.com|267-229-4017|78 La Follette Trail,Philadelphia,Pennsylvania|Account Representative II|7/7/2021|
|SMITTY BULMER|522|divorced|sbulmergm@addthis.com||23370 Forest Dale Street,Pittsburgh,Pennsylvania|VP Marketing|9/25/2017|
|LEONORE BOOTHJARVIS||married|lboothjarvisi2@bloglines.com|713-618-0516|33110 Luster Plaza,Houston,Texas|Sales Representative|6/13/2022|
|AUNDREA VILLAR|277|married|avillarm8@privacy.gov.au|571-942-0462|58201 Utah Terrace,Arlington,Virginia|Senior Sales Associate|6/28/2012|
|CHERY BATISSE||divorced|cbatissen3@bandcamp.com|804-431-7226|604 Elgar Way,Richmond,Virginia|VP Product Management|7/30/2012|
|ERINA AUBERT|288|married|eaubertqp@cargocollective.com|615-711-2470|2597 Hallows Road,Nashville,Tennessee|Automation Specialist II|11/2/2012|
|BALDWIN RIPPEN|588|single|brippen1z@nationalgeographic.com|912-469-5562|2 Esker Alley,Savannah,Georgia|Web Developer II|12/1/2015|
|CHERISE KRISTOFFERSSON|599|divorced|ckristoffersson59@sun.com|806-779-9348|72793 Northridge Park,Lubbock,Texas|Director of Sales|8/2/2021|
|THORNDIKE PORTINGALE|677|married|tportingale9n@nsw.gov.au|941-186-3805|9011 Huxley Plaza,Sarasota,Florida|Statistician II|2/16/2019|
|HASKELL BRADEN|322|divorced|hbradenri@freewebs.com|510-963-9848|35005 Waubesa Crossing,Berkeley,California|Dental Hygienist|11/4/2015|
|MONTAGUE LATHAM|644|married|mlathame5@dailymotion.com|210-522-8041|0 Buhler Plaza,San Antonio,Texas|Administrative Officer|2/13/2021|
|VIRGINA HUBBOCK||single|vhubbockep@ed.gov|540-535-0069|7 Schmedeman Center,Roanoke,Virginia|Media Manager I|7/6/2021|
|ALVA DELL 'ORTO|411|married|adellhp@yale.edu|951-142-9340|10 Carpenter Lane,Riverside,California|Food Chemist|3/10/2019|
|DENNI STALLARD|633|single|dstallardl9@devhub.com|816-567-5883|73737 Kinsman Street,Saint Joseph,Missouri|Nuclear Power Engineer|7/3/2018|
|CATHRINE JONSON|222|married|cjonsonol@aboutads.info|559-318-4841|4147 Swallow Hill,Fresno,California|Speech Pathologist|4/26/2022|
|JORI SANZ|399|married|jsanz3i@google.cn|904-906-7537|99 West Crossing,Jacksonville,Florida|Professor|2/15/2012|
|CARLYE GRAEBER|555|married|cgraeber6n@quantcast.com|214-345-1363|8 Dexter Junction,Dallas,Texas|Actuary|3/10/2021|
|SHURWOOD STRUTLEY|544|married|sstrutley9w@craigslist.org|804-636-0234|7779 Main Road,Richmond,Virginia|Nuclear Power Engineer|6/30/2014|
|CORBIN HILLAN|499|single|chillandg@time.com|267-229-4017|78 La Follette Trail,Philadelphia,Pennsylvania|Account Representative II|7/7/2021|
|SMITTY BULMER|522|divorced|sbulmergm@addthis.com||23370 Forest Dale Street,Pittsburgh,Pennsylvania|VP Marketing|9/25/2017|
|LEONORE BOOTHJARVIS||married|lboothjarvisi2@bloglines.com|713-618-0516|33110 Luster Plaza,Houston,Texas|Sales Representative|6/13/2022|
|AUNDREA VILLAR|277|married|avillarm8@privacy.gov.au|571-942-0462|58201 Utah Terrace,Arlington,Virginia|Senior Sales Associate|6/28/2012|
|CHERY BATISSE||divorced|cbatissen3@bandcamp.com|804-431-7226|604 Elgar Way,Richmond,Virginia|VP Product Management|7/30/2012|
|ERINA AUBERT|288|married|eaubertqp@cargocollective.com|615-711-2470|2597 Hallows Road,Nashville,Tennessee|Automation Specialist II|11/2/2012|
|BALDWIN RIPPEN|588|single|brippen1z@nationalgeographic.com|912-469-5562|2 Esker Alley,Savannah,Georgia|Web Developer II|12/1/2015|
|CHERISE KRISTOFFERSSON|599|divorced|ckristoffersson59@sun.com|806-779-9348|72793 Northridge Park,Lubbock,Texas|Director of Sales|8/2/2021|
|THORNDIKE PORTINGALE|677|married|tportingale9n@nsw.gov.au|941-186-3805|9011 Huxley Plaza,Sarasota,Florida|Statistician II|2/16/2019|
|HASKELL BRADEN|322|divorced|hbradenri@freewebs.com|510-963-9848|35005 Waubesa Crossing,Berkeley,California|Dental Hygienist|11/4/2015|
|MONTAGUE LATHAM|644|married|mlathame5@dailymotion.com|210-522-8041|0 Buhler Plaza,San Antonio,Texas|Administrative Officer|2/13/2021|
|VIRGINA HUBBOCK||single|vhubbockep@ed.gov|540-535-0069|7 Schmedeman Center,Roanoke,Virginia|Media Manager I|7/6/2021|
|ALVA DELL 'ORTO|411|married|adellhp@yale.edu|951-142-9340|10 Carpenter Lane,Riverside,California|Food Chemist|3/10/2019|
|DENNI STALLARD|633|single|dstallardl9@devhub.com|816-567-5883|73737 Kinsman Street,Saint Joseph,Missouri|Nuclear Power Engineer|7/3/2018|
|CATHRINE JONSON|222|married|cjonsonol@aboutads.info|559-318-4841|4147 Swallow Hill,Fresno,California|Speech Pathologist|4/26/2022|
|JORI SANZ|399|married|jsanz3i@google.cn|904-906-7537|99 West Crossing,Jacksonville,Florida|Professor|2/15/2012|
|CARLYE GRAEBER|555|married|cgraeber6n@quantcast.com|214-345-1363|8 Dexter Junction,Dallas,Texas|Actuary|3/10/2021|
|SHURWOOD STRUTLEY|544|married|sstrutley9w@craigslist.org|804-636-0234|7779 Main Road,Richmond,Virginia|Nuclear Power Engineer|6/30/2014|
|CORBIN HILLAN|499|single|chillandg@time.com|267-229-4017|78 La Follette Trail,Philadelphia,Pennsylvania|Account Representative II|7/7/2021|
|SMITTY BULMER|522|divorced|sbulmergm@addthis.com||23370 Forest Dale Street,Pittsburgh,Pennsylvania|VP Marketing|9/25/2017|
|LEONORE BOOTHJARVIS||married|lboothjarvisi2@bloglines.com|713-618-0516|33110 Luster Plaza,Houston,Texas|Sales Representative|6/13/2022|
|AUNDREA VILLAR|277|married|avillarm8@privacy.gov.au|571-942-0462|58201 Utah Terrace,Arlington,Virginia|Senior Sales Associate|6/28/2012|
|CHERY BATISSE||divorced|cbatissen3@bandcamp.com|804-431-7226|604 Elgar Way,Richmond,Virginia|VP Product Management|7/30/2012|
|ERINA AUBERT|288|married|eaubertqp@cargocollective.com|615-711-2470|2597 Hallows Road,Nashville,Tennessee|Automation Specialist II|11/2/2012|
|BALDWIN RIPPEN|588|single|brippen1z@nationalgeographic.com|912-469-5562|2 Esker Alley,Savannah,Georgia|Web Developer II|12/1/2015|
|CHERISE KRISTOFFERSSON|599|divorced|ckristoffersson59@sun.com|806-779-9348|72793 Northridge Park,Lubbock,Texas|Director of Sales|8/2/2021|
|THORNDIKE PORTINGALE|677|married|tportingale9n@nsw.gov.au|941-186-3805|9011 Huxley Plaza,Sarasota,Florida|Statistician II|2/16/2019|
|HASKELL BRADEN|322|divorced|hbradenri@freewebs.com|510-963-9848|35005 Waubesa Crossing,Berkeley,California|Dental Hygienist|11/4/2015|
|MONTAGUE LATHAM|644|married|mlathame5@dailymotion.com|210-522-8041|0 Buhler Plaza,San Antonio,Texas|Administrative Officer|2/13/2021|
|VIRGINA HUBBOCK||single|vhubbockep@ed.gov|540-535-0069|7 Schmedeman Center,Roanoke,Virginia|Media Manager I|7/6/2021|
|ALVA DELL 'ORTO|411|married|adellhp@yale.edu|951-142-9340|10 Carpenter Lane,Riverside,California|Food Chemist|3/10/2019|
|DENNI STALLARD|633|single|dstallardl9@devhub.com|816-567-5883|73737 Kinsman Street,Saint Joseph,Missouri|Nuclear Power Engineer|7/3/2018|
|CATHRINE JONSON|222|married|cjonsonol@aboutads.info|559-318-4841|4147 Swallow Hill,Fresno,California|Speech Pathologist|4/26/2022|
|JORI SANZ|399|married|jsanz3i@google.cn|904-906-7537|99 West Crossing,Jacksonville,Florida|Professor|2/15/2012|
|CARLYE GRAEBER|555|married|cgraeber6n@quantcast.com|214-345-1363|8 Dexter Junction,Dallas,Texas|Actuary|3/10/2021|
|SHURWOOD STRUTLEY|544|married|sstrutley9w@craigslist.org|804-636-0234|7779 Main Road,Richmond,Virginia|Nuclear Power Engineer|6/30/2014|
|CORBIN HILLAN|499|single|chillandg@time.com|267-229-4017|78 La Follette Trail,Philadelphia,Pennsylvania|Account Representative II|7/7/2021|
|SMITTY BULMER|522|divorced|sbulmergm@addthis.com||23370 Forest Dale Street,Pittsburgh,Pennsylvania|VP Marketing|9/25/2017|
|LEONORE BOOTHJARVIS||married|lboothjarvisi2@bloglines.com|713-618-0516|33110 Luster Plaza,Houston,Texas|Sales Representative|6/13/2022|
|AUNDREA VILLAR|277|married|avillarm8@privacy.gov.au|571-942-0462|58201 Utah Terrace,Arlington,Virginia|Senior Sales Associate|6/28/2012|
|CHERY BATISSE||divorced|cbatissen3@bandcamp.com|804-431-7226|604 Elgar Way,Richmond,Virginia|VP Product Management|7/30/2012|
|ERINA AUBERT|288|married|eaubertqp@cargocollective.com|615-711-2470|2597 Hallows Road,Nashville,Tennessee|Automation Specialist II|11/2/2012|
|BALDWIN RIPPEN|588|single|brippen1z@nationalgeographic.com|912-469-5562|2 Esker Alley,Savannah,Georgia|Web Developer II|12/1/2015|
|CHERISE KRISTOFFERSSON|599|divorced|ckristoffersson59@sun.com|806-779-9348|72793 Northridge Park,Lubbock,Texas|Director of Sales|8/2/2021|
|THORNDIKE PORTINGALE|677|married|tportingale9n@nsw.gov.au|941-186-3805|9011 Huxley Plaza,Sarasota,Florida|Statistician II|2/16/2019|
|HASKELL BRADEN|322|divorced|hbradenri@freewebs.com|510-963-9848|35005 Waubesa Crossing,Berkeley,California|Dental Hygienist|11/4/2015|
|MONTAGUE LATHAM|644|married|mlathame5@dailymotion.com|210-522-8041|0 Buhler Plaza,San Antonio,Texas|Administrative Officer|2/13/2021|
|VIRGINA HUBBOCK||single|vhubbockep@ed.gov|540-535-0069|7 Schmedeman Center,Roanoke,Virginia|Media Manager I|7/6/2021|
|ALVA DELL 'ORTO|411|married|adellhp@yale.edu|951-142-9340|10 Carpenter Lane,Riverside,California|Food Chemist|3/10/2019|
|DENNI STALLARD|633|single|dstallardl9@devhub.com|816-567-5883|73737 Kinsman Street,Saint Joseph,Missouri|Nuclear Power Engineer|7/3/2018|
|CATHRINE JONSON|222|married|cjonsonol@aboutads.info|559-318-4841|4147 Swallow Hill,Fresno,California|Speech Pathologist|4/26/2022|
|JORI SANZ|399|married|jsanz3i@google.cn|904-906-7537|99 West Crossing,Jacksonville,Florida|Professor|2/15/2012|
|CARLYE GRAEBER|555|married|cgraeber6n@quantcast.com|214-345-1363|8 Dexter Junction,Dallas,Texas|Actuary|3/10/2021|
|SHURWOOD STRUTLEY|544|married|sstrutley9w@craigslist.org|804-636-0234|7779 Main Road,Richmond,Virginia|Nuclear Power Engineer|6/30/2014|
|CORBIN HILLAN|499|single|chillandg@time.com|267-229-4017|78 La Follette Trail,Philadelphia,Pennsylvania|Account Representative II|7/7/2021|
|SMITTY BULMER|522|divorced|sbulmergm@addthis.com||23370 Forest Dale Street,Pittsburgh,Pennsylvania|VP Marketing|9/25/2017|
|LEONORE BOOTHJARVIS||married|lboothjarvisi2@bloglines.com|713-618-0516|33110 Luster Plaza,Houston,Texas|Sales Representative|6/13/2022|
|AUNDREA VILLAR|277|married|avillarm8@privacy.gov.au|571-942-0462|58201 Utah Terrace,Arlington,Virginia|Senior Sales Associate|6/28/2012|
|CHERY BATISSE||divorced|cbatissen3@bandcamp.com|804-431-7226|604 Elgar Way,Richmond,Virginia|VP Product Management|7/30/2012|
|ERINA AUBERT|288|married|eaubertqp@cargocollective.com|615-711-2470|2597 Hallows Road,Nashville,Tennessee|Automation Specialist II|11/2/2012|
|BALDWIN RIPPEN|588|single|brippen1z@nationalgeographic.com|912-469-5562|2 Esker Alley,Savannah,Georgia|Web Developer II|12/1/2015|
|CHERISE KRISTOFFERSSON|599|divorced|ckristoffersson59@sun.com|806-779-9348|72793 Northridge Park,Lubbock,Texas|Director of Sales|8/2/2021|
|THORNDIKE PORTINGALE|677|married|tportingale9n@nsw.gov.au|941-186-3805|9011 Huxley Plaza,Sarasota,Florida|Statistician II|2/16/2019|
|HASKELL BRADEN|322|divorced|hbradenri@freewebs.com|510-963-9848|35005 Waubesa Crossing,Berkeley,California|Dental Hygienist|11/4/2015|
|MONTAGUE LATHAM|644|married|mlathame5@dailymotion.com|210-522-8041|0 Buhler Plaza,San Antonio,Texas|Administrative Officer|2/13/2021|
|VIRGINA HUBBOCK||single|vhubbockep@ed.gov|540-535-0069|7 Schmedeman Center,Roanoke,Virginia|Media Manager I|7/6/2021|
|ALVA DELL 'ORTO|411|married|adellhp@yale.edu|951-142-9340|10 Carpenter Lane,Riverside,California|Food Chemist|3/10/2019|
|DENNI STALLARD|633|single|dstallardl9@devhub.com|816-567-5883|73737 Kinsman Street,Saint Joseph,Missouri|Nuclear Power Engineer|7/3/2018|
|CATHRINE JONSON|222|married|cjonsonol@aboutads.info|559-318-4841|4147 Swallow Hill,Fresno,California|Speech Pathologist|4/26/2022|

***** UPDATE age by using MODE 

UPDATE club_member_info_cleaned 
SET age = 40 where age < 18 or age >90 or age is NULL;





