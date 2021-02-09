<p style="text-align: center;"><strong>Presentation Outline:</strong></p>
<p><strong>INTRO</strong></p>
<ol>
<li>Project Overview</li>
<li>Datasets Used</li>
<li>Project Scope</li>
</ol>
<p><strong>EXTRACT</strong></p>
<ol>
<li>Data Collected</li>
<li>Data Purpose</li>
</ol>
<p><strong>TRANSFORM</strong></p>
<ol>
<li>Data Wrangling</li>
<ol>
<li>Cleaning</li>
<li>Joining</li>
<li>Filtering</li>
<li>Aggregating</li>
</ol>
</ol>
<p><strong>LOAD</strong></p>
<ol>
<li>Table Structures/Schemata</li>
</ol>
<p><strong>CONCLUSION:</strong></p>
<ol>
<li>Use Cases (Stories)</li>
<ol>
<li>3-5 explanations of how this data can be used</li>
</ol>
</ol>
<h2 style="text-align: center;">&nbsp;</h2>
<h2 style="text-align: center;">INTRO</h2>
<h3 style="text-align: center;">Project Overview</h3>
<p><strong>Team Members: </strong>Isma Adan, Tanner Pedretti, Andr&eacute;s Solano, Amy Wagar Cinch</p>
<p><strong>Project Title:</strong> ETL Project - Global Yelp Reviews</p>
<p><strong>Question(s) to Answer: </strong>Do businesses tend to receive <strong>better or worse </strong>reviews on <strong>specific dates</strong> or <strong>moon phases</strong>?</p>
<ul>
<li>Is there a statistically significant relationship between <strong>Yelp</strong><strong>reviews</strong> and the <strong>moon phase</strong> on the date of the review?</li>
<li>How frequently do people leave <strong>Yelp</strong> reviews on <strong>specific dates</strong>?</li>
</ul>
<h3 style="text-align: center;">Datasets Used</h3>
<p><a href="https://www.kaggle.com/z5025122/yelp-csv" target="_blank" rel="noopener">Yelp Data</a> (Kaggle.com)</p>
<ol>
<li><strong>Overview:</strong></li>
<ol>
<li>42,153 businesses</li>
<li>1,048,575 user reviews</li>
</ol>
</ol>
<ol>
<ol>
<li><strong>Data points used:</strong></li>
<ol>
<li><strong>Business</strong></li>
<ol>
<li><em>Business ID</em></li>
</ol>
</ol>
</ol>
<ol>
</ol>
<ol>
<ol>
<ol>
<ol>
<li><em>City</em></li>
<li><em>State</em></li>
<li><em>Categories</em> (Business Type)</li>
</ol>
<li><strong>Reviews</strong></li>
<ol>
<li><em>Business ID</em></li>
<li><em>Stars</em></li>
</ol>
</ol>
</ol>
</ol>
<p><em>Dates</em></p>
<p><a href="https://www.worldweatheronline.com/developer/api/docs/astronomy-api.aspx" target="_blank" rel="noopener">Moon Phase API</a> (WorldWeatherOnline.com)</p>
<ol>
<li><strong>Overview:</strong></li>
<ol>
<li>API for accessing astronomy information for specific dates</li>
</ol>
</ol>
<ol>
<ol>
<li><strong>Data points used:</strong></li>
</ol>
</ol>
<p><strong>Moon Phase</strong></p>
<ol>
<ol>
<ol>
<ol>
<li><em>New</em></li>
<li><em>Waxing Crescent</em></li>
<li><em>First Quarter</em></li>
<li><em>Waxing Gibbous</em></li>
<li><em>Full</em></li>
<li><em>Waning Gibbous</em></li>
<li><em>Third Quarter</em></li>
<li><em>Waning Crescent</em></li>
</ol>
</ol>
</ol>
</ol>
<p><strong>Date</strong></p>
<ol>
<ol>
<ol>
<li><em>Date of moon phase corresponding to Yelp data timeframe.</em></li>
</ol>
</ol>
</ol>
<p>&nbsp;</p>
<h2 style="text-align: center;">EXTRACT</h2>
<h3 style="text-align: center;">Data Collected</h3>
<p>Yelp <span style="text-decoration: underline;">reviews</span> for <span style="text-decoration: underline;">businesses</span> within the dataset, along with the <span style="text-decoration: underline;">moon phase</span> on the date of each review.</p>
<ol>
<li><strong>Timeframe:</strong></li>
<ol>
<li>Dataset covered reviews from <strong>2004-2014</strong></li>
<li>Dates selected for Moon Phase ranged from <strong>2009-2014</strong></li>
</ol>
</ol>
<ol>
<li><strong>Geographic Scope:</strong></li>
<ol>
<li>10 &ldquo;States&rdquo; around the world:</li>
<ol>
<li><strong>USA</strong></li>
<ol>
<li><em>Arizona</em></li>
<li><em>California</em></li>
<li><em>Georgia</em></li>
<li><em>Massachusetts</em></li>
<li><em>Minnesota</em></li>
<li><em>Nevada</em></li>
<li><em>New York</em></li>
<li><em>Wisconsin</em></li>
</ol>
<li><strong>International:</strong></li>
<ol>
<li><em>Ontario, Canada</em></li>
<li><em>Edinburgh, UK</em></li>
</ol>
</ol>
</ol>
</ol>
<ol>
<li><strong>Specific Dates Pulled:</strong></li>
<ol>
<li>Selected randomly for cross-reference with Moon Phase API</li>
<ol>
<li><em>Valentine&rsquo;s Day (February 14th)</em></li>
<li><em>Mother&rsquo;s Day (March in UK, May in US; varies each year)</em></li>
<li><em>April 20th</em></li>
<li><em>Black Friday (November; varies each year)</em></li>
<li><em>Christmas Eve (December 24th)</em></li>
</ol>
</ol>
</ol>
<h3 style="text-align: center;">Data Purpose</h3>
<p><strong>Purpose of the Data</strong>:</p>
<ol>
<li><span style="text-decoration: underline;">Business data</span> frames the businesses to analyze</li>
<li><span style="text-decoration: underline;">Review data</span> provides a quantitative measure for the quality of a customer&rsquo;s overall experience</li>
<li><span style="text-decoration: underline;">Astronomy data</span> helps us to analyze potential trends or relationships between review scores and moon phases</li>
</ol>
<p>&nbsp;</p>
<h2 style="text-align: center;">TRANSFORM</h2>
<h3 style="text-align: center;">Data Wrangling</h3>
<p><strong>Cleaning:</strong></p>
<ol>
<li>The Yelp business data consisted of 105 columns and we needed to clean it up to the specific columns needed. Similarly, the Yelp&nbsp; reviewer data consisted of 10 columns and we cleaned that up by selecting the columns we needed for the project.&nbsp;</li>
<li>Created a business_df and review_df from filter columns.</li>
</ol>
<p><strong>Joining:</strong></p>
<ol>
<li>Joined the Business data and Reviewer dataframe on the <strong>business_id</strong> column to create a new dataframe called Yelp_df.</li>
<li>Dropped for duplicates&nbsp;</li>
</ol>
<p><strong>Filtering</strong></p>
<ol>
<li>Filtered the business data for the Business ID, State, City and Categories columns. Created a dataframe reflecting filtered data.</li>
<li>Filtered the reviewer data for Business ID, User ID, Stars(rating) and Date (of review). Created a dataframe reflecting filtered data.</li>
<li>Excluded non-restaurant businesses</li>
</ol>
<p><strong>Aggregating</strong></p>
<ol>
<li>Statistical summary on the business data to obtain basic statistical details on the business dataset.</li>
</ol>
<p>&nbsp;</p>
<p><strong>Roadblocks</strong></p>
<p>&nbsp;</p>
<p><strong>Dataset Size</strong></p>
<ol>
<ol>
<li>We initially found a dataset that was quite robust (5.2 million reviews, 174,000+ businesses) and touted diversity through a sample size of 11 global metropolitan areas.</li>
<li>We soon came to find out that this dataset was too large for us to handle. After settling on this option, we eventually had to pivot to one that was more manageable for the operations required on this project.</li>
</ol>
</ol>
<ol>
<li><strong>Data Diversity</strong></li>
<ol>
<li>As a result of us having to change to a new dataset, we then gave up the large sample size AND diversity</li>
<li>The actual dataset being used on this project is heavily dominated by businesses and reviews within the USA states of AZ and NV.</li>
</ol>
</ol>
<ol>
<ol>
<li><strong>Data Quality</strong></li>
<ol>
<li>Much of the data collection on Yelp seems to have been open-ended inputs rather than finite selections/inputs. While this allows for users to express themselves and their experiences freely, certain areas (city, state) are better suited for finite-selection inputs rather than open-text inputs.</li>
<ol>
<li>Ex: The city of &ldquo;Las Vegas&rdquo; had 15 different entries</li>
<li>Ex: In one entry, the city of &ldquo;Las Vegas&rdquo; was listed under the state &ldquo;NC&rdquo; instead of &ldquo;NV&rdquo;</li>
</ol>
</ol>
</ol>
</ol>
<p><strong>API Documentation</strong></p>
<ol>
<ol>
<li>The Astronomy API that was used had very sparse documentation, and a lot of guessing and checking was necessary to pull data from it.&nbsp;</li>
</ol>
</ol>
<p>&nbsp;</p>
<h2 style="text-align: center;">LOAD</h2>
<h3 style="text-align: center;">Table Structures Schemata</h3>
<p><strong>Table Structure Explanation:</strong></p>
<ol>
<li>Combined tables by date (specific dates mentioned above)</li>
<ol>
<li><strong>Moon_cycles table</strong></li>
<li><strong>Yelp_table</strong></li>
</ol>
</ol>
<p>&nbsp;</p>
<h2 style="text-align: center;">CONCLUSION</h2>
<h3 style="text-align: center;">Use Cases</h3>
<p><strong>Use Cases:</strong></p>
<ol>
<li>This data would be helpful to see what ratings businesses receive on dates such as Valentine&rsquo;s Days or Black Fridays or moon cycles.</li>
<li>This data would be useful to compare of different business categories get review on Yelp based on moon cycle or special holiday dates&nbsp;</li>
<li>This data would be useful to get historical data on how often people leave yelp reviews on certain holidays and the type of ratings they give businesses.</li>
</ol>
