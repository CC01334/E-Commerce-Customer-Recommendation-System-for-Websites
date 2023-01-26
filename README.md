<!-- This is the markdown template for the final project of the Building AI course, 
created by Reaktor Innovations and University of Helsinki. 
Copy the template, paste it to your GitHub README and edit! -->

E-Commerce Customer Recommendation System for Websites

## Summary
 AI has had a significant impact on e-commerce and the way they are structured. A great example of an e-commerce platform implementing Artificial Intelligence would be Amazon's customer recommendation system. Because of the improved customer experience, this customer recommendation system has greatly aided the platform in increasing its revenue.

## Background
A recommendation system usually has two types of methods to work with, content-based and collaborative filtering. A content-based system usually takes the pre-existing similarities and gives recommendations on the basis of those parameters. A collaborative filtering method, however, recognizes patterns and trends in earlier and other user-item interactions and makes comparable recommendations to a current user based on those interactions.

More and more people prefer shopping online rather than going to retail stores. The main idea of online shopping is to ease the shopping experience by getting personalized recommendations of products. This is also what the E-Commerce websites are expected to do. The present recommendation system is ineffective because it doesn’t handle three main problems: Limited resource, cold start and data valid time. The recommendation system consists of user model, recommended model and recommendation algorithm. This paper includes the proposed model that focuses on the improvement to the recommendation algorithm by providing solutions to limited resource and cold start problem. The proposed system aims at better customer satisfaction.

## How is it used?

Recommender systems in eCommerce enhance loyalty by creating a value-added and personal relationship between the site and the buyer. eCommerce websites invest in learning about their customers, implementing recommender systems to put into action learning and present buyer interfaces that go with customer needs.A recommender system, or a recommendation system (sometimes replacing 'system' with a synonym such as platform or engine), is a subclass of information filtering system that provide suggestions for items that are most pertinent to a particular user. Typically, the suggestions refer to various decision-making processes, such as what product to purchase, what music to listen to, or what online news to read. Recommender systems are particularly useful when an individual needs to choose an item from a potentially overwhelming number of items that a service may offer. e-commerce, recommendation systems are a particularly important topic. This is because online stores have the possibility to increase their conversion rate through suitable recommendations and generate more sales. Many shop systems have integrated standard features for product recommendations.


This is how you create code examples:
```
# remove consecutive duplicates from list
def remove_consec_duplicates(raw_lst):
  previous_value = None
  new_lst = []

  for elem in raw_lst:
    if elem != previous_value:
        new_lst.append(elem)
        previous_value = elem
        
  return new_lst


def generate_sequential_products():
  # Rename columns
  data = raw_clickstream.rename(columns={"session ID": "session_id", "page 2 (clothing model)": "product_id"})
  # Remove sessions where only a single product is viewed
  data = data.groupby("session_id").filter(lambda x: len(x) > 1)
  # Group product view sequences in order by session id
  data = data.sort_values("order").groupby("session_id")["product_id"].apply(list)
  # Remove consecutive duplicate product views from the sequences genereated in the previous step
  data = data.apply(remove_consec_duplicates)

  #Convert series to data frame
  data = data.to_frame().reset_index().rename(columns={"product_id": "chronological_product_sequence"})

  return data
  -----------------------------------------------------------------------
  import pandas as pd
def raw_session_based_clickstream_data():
  data = pd.read_csv("examples/recommendation-system/e-shop clothing 2008.csv",delimiter = ';')
  return data

main()
```
------------------------------------------------------------------------------------------

## Challenges
A closely related issue is protecting these systems from manipulation by (sometimes even small but) especially active groups of users, whose interactions with the system can generate intense positive feedback, driving up the system’s rate of recommendations for specific items. A much-discussed effect of some recommender systems is their transformative impact on society. In particular, news recommender systems and social media filters, by nature of their design, run the risk of insulating users from exposure to different viewpoints, creating self-reinforcing biases and “filter bubbles” that are damaging to the normal functioning of public debate, group deliberation, and democratic institutions.This feature of recommender systems can have negative effects on social utility.

The literature on the topic proposes a range of approaches to increase the diversity of recommendations. A point noted by several authors is that news recommendation systems, in particular, must reach a trade-off between the expected relevance to the user and diversity when generating personalised recommendations based on pre-specified user preferences or behavioural data. Starting with privacy, the main challenge that is linked with privacy violations is the possibility of unfair or otherwise malicious uses of personal data to target individual users. Thus, from our review, it emerges that privacy concerns may be best conceptualised as exposure to risk. Moreover, the types of risk to which privacy violations expose users fall mainly under the category of rights violations, such as unfair targeting and use of manipulative techniques.The opacity about which and whose values are at stake in recommender systems hinders the possibility of designing better systems that can also promote socially preferable outcomes and improve the balance between individual and non-individual utilities.

Among the reviewed articles, the ones addressing privacy, fairness and opacity come predominantly from computer science. This is in line with the general trends in the field of algorithmic approaches to decision-making, and the presence of established metrics and technical approaches to address these challenges.

## What next?

How could your project grow and become something even more? What kind of skills, what kind of assistance would you  need to move on? 

To build the recommender, we will use Surprise, a Python scikit package built for collaborative filtering. As often happens with real-world data, this dataset is not perfectly constructed for creating a collaborative recommendation system. A big challenge here is that almost 90% of the users are first-time customers which means that we don’t have previous ratings from them to identify products that like. Instead, we will separate the dataset into repeat and first time users and feed only the repeat customers into the collaborative filtering model. For first-time customers, we can still provide recommendations but they will be more generic, focused on item popularity and the user’s location. baseline_only.BaselineOnly- Algorithm predicting the baseline estimate for given user and item.

## Acknowledgments

* list here the sources of inspiration 
* Artificial Intelligence and Machine Learning 
* Coding 
