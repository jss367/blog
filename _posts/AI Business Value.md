One of the most important things that machine learning (ML) practitioners can do is to help customers, product managers, and senior leadership understand the business value that machine learning can apply. Right now, we are deep in the world of unnecessary hype in artificial intelligence where it is being applied to many [projects that don't make sense](links to ai toilet, etc.). This means that there will be demand for ML use cases that don't make sense, and ML practitioners should help others to avoid these use cases.

I thought it was worthwhile to talk a little bit about when ML is and isn't useful.

The current state-of-the-art in machine learning, broadly speaking, does things well but not perfectly. If you need to translate a paragraph and figure out basically what it means, machine learning can help you. If you need to translate a paragraph and get it exactly right, machine learning cannot do that. The same is true for vision. If you want to count cats from a live video feed, machine learning can get you most of the way and allow you to determine trends over time. But if you need the exact answer, I wouldn't use machine learning.

Why does this matter? Because it illustrates a key difference that can drive business value. If the result you are looking for needs to be perfect, the value is low. Let's say you are translating messages between world leaders. You could certainly use AI for this, but because the text will need to be reread and the resulting translation be corrected by a professional translater, the value added by the AI is low (although not necessarily 0). If, however, you would like to know if the number of cats in a region is decreasing or increasing in time




Convincing people that their data doesn't need to be perfect. In many business cases, perhaps even the majority, people are interested in change over time. Say you work at a social media company where users share messages. The executives decide they want to reduce the amount of unfriendly language, so they decided to roll out an anti-bullying campaign. Your job is to measure whether this campaign works or not. AI is the perfect tool for this case. You don't need to know the exact number of rude messages, or the exact sentiment of messages, just the change. So you use AI to measure the overall sentiment of messages on the platform as well as count the number of rude messages. As long as the model is working well, there is no need for a human to review each message.

I will make a quick caveat that there still needs to be basic spot checks or the like of the model. There is always a need to continuously review the performance of machine learning models. This is because of 1. if the input distribution in production changes from what it used to be, the model will most likely perform worse, and 2. because these algorithms are often widely scaled, there should be continuous testing on any system of this size. Netflix undergoes constant testing. Netflix has pioneered something called "Chaos Engineering", led by its Chaos Monkey tool. The point of the tool isn't 

### Customer Data Doesn't Need to Be *Perfect*

This brings me to one of the more difficult aspects of an ML practitioner's job. Customers you work with will have a pre-defined way of doing their jobs. That way is usually highly manually and not scalable. Your job is to scale this process using AI. But here's the catch, they couldn't possibly accept data that is any less than perfect. And, in many cases, they are wrong. And the tricky part is, it's your job to convince them of that. Let's say the customer is detecting wildlife with audio and currently has audio posts located throughout a wildlife park. Let's also say that the current state of the art on whatever wildlife they are interested in is good, but below human performance. They can't bear the thought of missing an animal call, but you have to convince them that the benefit of using AI, which would let you add many more audio collection stations, outweighs the loss in accuracy. This can be difficult and depending on the customer, it might be impossible to convince them. That's why I said it might be the hardest part.

One possible solution you have to reach common ground is to find out exactly what they don't want to miss. They're OK with your ML model's performance on galahs, Australian ringnecks, and little corellas, but they couldn't bear the thought of missing a rare night parrot. So you create a high recall network by dropping your threshold for night parrots to something quite low and have a professional go over all the possible records it found. 


### Compute Costs Will Cut Into Your Margins


You need data and compute. Are you paying for the data? You need to incorporate that into your price. Are you paying for the compute? Unless it's running on the customer's infrastructure (like their cell phone), you are, either in electricity and costs to host or in cloud computing.




## Bad Examples

Doing you taxes. This should be done deterministically. Would also need to be reviewed by a human.



https://mebassett.info/ai-useless-for-business

