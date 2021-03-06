![Elasticworks.](https://raw.githubusercontent.com/skrusche63/spark-fm/master/images/predictiveworks.png)

**Predictiveworks.** is an open ensemble of predictive engines and has been made to cover a wide range of today's analytics requirements. **Predictiveworks.**  brings the power of predictive analytics to Elasticsearch.


## Reactive Context-Aware Analysis Engine

![Factorization Machines Overview](https://raw.githubusercontent.com/skrusche63/spark-fm/master/images/factorization-machines-overview.png)

The Context-Aware Analysis Engine is one of the nine members of the open ensemble and has a strong focus on context-sensitive data and interactions in 
multi-dimensional datasets. It is the key to the next-generation of personalized predictions and customer relationships.

### Examples

The Context-Aware Analysis Engine is based on factorization machines. These are multi-purpose predictors that are applicable to many different application areas. 
Below we describe some selected uses cases that we think are of common interest, and we certainly do not claim that the list of use cases is complete.

##### Context-Aware Recommendations

Recommender systems are an important feature of modern websites. Especially commercial sites benefit from a boost in customer loyalty, click-through rates and revenues when using recommender systems.

The majority of existing approaches to recommender systems focus on recommending the most relevant items to individual users and do not take into account any contextual information, such as time, place and the company of other people.

For personalized recommendations, however, it is not sufficient to consider only *users* and their engagement on a set of *items*. It is important to incorporate contextual information in order to recommend items to users *under certain circumstances*, and make those recommendations more personalized.

> For example, using a temporal context, a travel recommender system would provide vacation recommendations in the winter, that can be very different from those in the summer.

##### Semantic Concept Prediction

Semantic concepts are a commonly used means to specify the meaning of web pages. These concepts are either explicitly provided by the respective authors (e.g in terms of metadata tags) or derived by sophisticated linguistic and semantic techniques. The latter thereby rely on specific terminologies, such as taxonomies, term-concept maps or even domain specific ontologies.

Different website owners usually assign semantic concepts that refer to different terminologies. The hidden semantics of two different articles may be the same, but the assigned concepts differ and are controlled by different authors. Due to this situation, the content profiles associated with these articles are different.

Factorization Machines are an appropriate means to overcome this concept heterogeneity and help to improve semantic interoperability.



### Factorization Machines

Matrix factorization (MF) approaches to recommendations have become very popular as they usually outperform traditional k-nearest neighbor methods. MF, however, is context-unaware.

The most approaches to take contextual information into account focus on contextual pre- or post-filtering where a standard context-unaware technique, such as MF is applied to the filter data.

New approaches extend the 2-dimensional space (user,item,rating) `R: U x I -> R` to an n-dimensional space (user,item,c1,c2,...,rating) `R: U x I x C1 x C2 x ... -> R`, where *c1*, *c2* etc describe contextual dimensions. These approaches extend matrix models (MF) to tensor models (TF).

Recently a recommendation approach, called *Multiverse Recommendation*, as been proposed that uses Tucker decomposition to factorize these n-dimensional tensor models. However, a drawback of this approach is its computational complexity.

Therefore, we suggest to build a context-aware recommender system on Factorization Machines (FM), recently introduced by Steffen Rendle. This approach results in fast context-aware recommendations as the model equation of FMs can be computed in linear time both in the number of contextual parameters and the selected factorization size.


### Factorization Machines in Spark

This is an implementation of Factorization Machines based on Scala and Apache Spark. It actually uses stochastic gradient descent (SGD) as a learning method while training the model parameters. 

From http://libfm.org: 

> Factorization machines (FM) are a generic approach that allows to mimic most factorization models by feature engineering. This way, factorization machines combine the generality of feature engineering with the superiority of factorization models in estimating interactions between categorical variables of large domain.


For more details, please refer to:
Steffen Rendle (2012): Factorization Machines with libFM, in ACM Trans. Intell. Syst. Technol., 3(3), May.
