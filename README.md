<h1>Amazon Vine Analysis</h1>
<h2>Overview of the Analysis</h2>
<p>SellBy, like many other companies, pays a small fee to Amazon who provides their products to Amazon Vine members.  These members are then required to publish a review of the product.  The purpose of this analysis is to determine if there is any bias toward favorable reviews from Vine members.  Amazon provides datasets, based on categories, which includes reviews from both Vine and non-Vine members. For the purposes of this review the dataset for the luggage category was selected for analysis.</p>
<h2>Data</h2>
<ul>
<li>dataset - https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Luggage_v1_00.tsv.gz</li>
</ul>
<h2>Results</h2>
<p>Prior to completing the analysis the following transformations to the dataset were completed:
<ul>
<li>The data was filtered to retrieve all rows where the total votes were equal to or greater than 20 as it is assumed that these reviews are morely likely to be helpful.  The filtered dataset was saved into a new dataframe.</li>
<li>This new dataframe was then filtered to only include rows where the helpful votes divided by total votes were greater than or equal to 50%.</li>
</ul>
<h4>Results on Filtered Dataset</h4>
<ul>
<li>As can be seen in the image below there were 21 reviews from Vine members.</li>
</ul>
<img src="https://github.com/bedwardssmith/Amazon_Vine_Analysis/blob/main/Resources/total_reviews_vine.png" alt="total_reviews_vine">
<ul>
<li>As can be seen in the image below there were 6,690 reviews from non-Vine members.</li>
</ul>
<img src="https://github.com/bedwardssmith/Amazon_Vine_Analysis/blob/main/Resources/total_reviews_non_vine.png" alt="total_reviews_none_vine">
<ul>
<li>Of the 21 reviews posted by Vine members 10 of these were 5 star reviews; refer to image below.</li>
</ul>
<img src="https://github.com/bedwardssmith/Amazon_Vine_Analysis/blob/main/Resources/five_star_reviews_vine.png" alt="vine_5_star_reviews>
<ul>
<li>Of the 6,690 reviews posted by non-Vine members 3,448 of these were 5 star reviews; refer to image below.</li>
</ul>
<img src="https://github.com/bedwardssmith/Amazon_Vine_Analysis/blob/main/Resources/five_star_review_non_vine.png" alt="non_vine_five_star_reviews">
<ul>
<li>The percentage of 5 star reviews posted by Vine members were 47.6%; refer to image below.</li>
</ul>
<img src="https://github.com/bedwardssmith/Amazon_Vine_Analysis/blob/main/Resources/percentage_five_star_reviews_vine.png" alt="percentage_five_star_reviews_vine">
<ul>
<li>The percentage of 5 star reviews posted by non-Vine members were 51.5%; refer to image below.</li>
</ul>
<img src="https://github.com/bedwardssmith/Amazon_Vine_Analysis/blob/main/Resources/percentage_five_star_reviews_non_vine.png" alt="percente_five_star_reviews_non_vine">
<br>
<h2>Summary</h2>
<p>Based on the results of the analysis there does not appear to be any positivity bias for reviews in the Vine program as the percentage of 5 star reviews was higher for non- Vine members than for Vine members; 51.5% and 47.6% respectively.  However, it is concerning that the total reviews posted by Vine members are only 21 when looking at the filtered dataframe in comparison with the total reviews posted by non-Vine members of 6,690.  Due to the limited number of reviews meeting the two original criteria, total vote count greater than or equal to 20 and helpful votes divided by total votes equal or greater than 50, I would recommend two additional analysis.  The first being to calculate total reviews, total 5 star reviews, and percentage of 5 star reviews for both the Vine program and non-Vine program on the original dataset; this has been completed within the section "Additional Analysis" below.  Additionally, I would recommend completing the same analysis on a different dataset to determine if the results are similiar.</p>
<h3>Additional Analysis</he>
<h4>Analysis of Vine program reviews using full dataset</h4>
<p>As reflected in the image below the total number of reviews from Vine members using the full dataset is 904, with the number of 5 star reviews being 472.  This provides a percentage of 52.2% of 5 star reviews posted by Vine members.  This is a slight increase from the 47.6% we calculated using the filtered dataset.</p>
<img src="https://github.com/bedwardssmith/Amazon_Vine_Analysis/blob/main/Resources/analysis_vine_program.png" alt="analysis vine proram"</>
<h4>Analysis of non-Vine program reviews using full dataset</h4>
<p>As reflected in the image below the total number of reviews from non-Vine members using the full dataset is 347,747, with the number of 5 star revview being 216,023.  This provides a percentage of 62.1% of 5 star reviews posted by non-Vine members.  This is a significant increase from the 51.5% we calculated using the filtered dataset.<p>
<img src="https://github.com/bedwardssmith/Amazon_Vine_Analysis/blob/main/Resources/analysis_not_vine_program.png" alt="analysis not vine program">
<h4>Results</h4>
<p>These results do not change my original conclusion that there does not appear to be any positivity bias for reviews in the Vine program as the percentage of 5 star reviews is higher for non-Vine members than for Vine members; 62.1% and 52.5% respectively.  However, by removing the filters from the dataset it does alleviate the concern as to the size of the dataset analyzed.</p>
