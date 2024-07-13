# Finding you next perfect house....

Renting, also known as hiring or letting, is an agreement where a payment is made for the temporary use of a good, service or property owned by another.
A gross lease is when the tenant pays a flat rental amount and the landlord pays for all property charges regularly incurred by the ownership. An example of 
renting is equipment rental. Renting can be an example of the sharing economy. Some of the top renting platforms available are:

* Apartments.com
* Zillow
* Zumper
* Avail
* Airbnb
* MagicBricks
* CraigList
* and many others ...........

In this exploratory data analysis, we compare a dataset which consists of various features about renting of houses available on these renting platforms listed by owners of these houses, 
and try to derieve some constructive conclusions by performing Descriptive statistics of the available features.

### Dataset Analysis:

* BHK: Number of Bedrooms, Hall, Kitchen.
* Rent: Rent of the Houses/Apartments/Flats.
* Size: Size of the Houses/Apartments/Flats in Square Feet.
* Floor: Houses/Apartments/Flats situated in which Floor and Total Number of Floors (Example: Ground out of 2, 3 out of 5, etc.)
* Area Type: Size of the Houses/Apartments/Flats calculated on either Super Area or Carpet Area or Build Area.
* Area Locality: Locality of the Houses/Apartments/Flats.
* City: City where the Houses/Apartments/Flats are Located.
* Furnishing Status: Furnishing Status of the Houses/Apartments/Flats, either it is Furnished or Semi-Furnished or Unfurnished.
* Tenant Preferred: Type of Tenant Preferred by the Owner or Agent.
* Bathroom: Number of Bathrooms.
* Point of Contact: Whom should you contact for more information regarding the Houses/Apartments/Flats.

The dataset does not contain any null values. Hence no technique for removing null or nan values is required in this case.
We will be treating only Rent and Size as the numerical features and all others as Categorical Features.

### Conclusions:

After performing Exploratory Data Analysis on this dataset, I have come to following hypothesis:
* As the rent for most of the houses is mostly less than 0.25M, hence listings of luxurious houses are rarely posted on the platform.
* Rent Feature is distributed just like salary in corporate, mostly taking average salaries and executive salaries are taken by just some.
* The rent for a 6BHK is comparitive to a 3BHK. This could potentially help in getting a great deal from the owner of these 6BHK homes.
* The dataset is based on metro cities where rents are usually high as compared to types of cities which have less level of facilities.
* The owners of these listings are not biased towards tenant preferred but just bachelors usually have to pay higher rent as compared to owners who accept only families or both families and bachelors.
* For low priced houses, contacting the owners is preferred mode of contact as it helps them in having comission. Very few listings are where builder have to be contacted as rarely builders will be directly renting houses.
* The dataset had high class imbalance for most of the categories.
* Medium rent increases first with increase in number of bathrooms in the house and then decreses. This could help in identify houses that are large as they contain large number of bathrooms as well as have less rent.

### Feature Engineering:

In Floor feature, we have a lot of unique values. So we will be dividing it into two features. These two features will be Rent Floor and Total Floor in the building. This can be done by finding " out of " pattern in the Floor string. But in some cases, this " out of string " is not present.
The values present in this case are ("1" -> 2 instances, "3" -> 1 instance, "Ground" -> One instance). In total these are just 4 instances and we can safely remove them to make our training set more accurate and error free.

Lets Drop the Area Locality feature as we wont be using it.

In the following dataset we have to One Hot encode the following columns:

* Area Type
* City
* Furnishing Status
* Tenant Preferred
* Point of Contact

If we convert it into categorical categories only then the machine learning model might find correlation among categories which are close to each other even when they are not correlated.
