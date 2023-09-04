# 4.4 Questions to ask yourselves when building and classifying questions
___

Sometimes when we are building questions, it may be a little confusing classifying them into one of the aforementioned types (type1- type*). The following questions will help you when classifying your questions.

> This is a little guide and its purpose it is to help you, it is not an exhaustive guide with all the possible questions and answers for the classification process.

For this guide we will present Sam. He is a student of last semester of Systems and Computing Engineering. Sam is attending the Mobile App Development course and he is trying to make his best effort formulating 40 to 50 business questions, which is a good number to start. But he is having some troubles formulating the questions; he is asking himself are these questions valid?, are they good for my business?. Because of this, he asks for advice to some partners and professors; someone tells him that he could do the following exercise:

>Imagine that you have a twin, called Sam2. Your twin  always helps you when you are in trouble, making you some questions to help you spot possible problems or good ideas for a problem. This time, Sam2 is an expert in data analytics and will help you spot problems in your questions, refine them and also classify the questions into the respective type.  In order to help Sam, Sam2 will ask Sam some questions

<p align="center">
  <img width="460" height="300" src="../assets/chapter4/Sam2_intro.png">
</p>

Sam agrees to try this approach and took 8 initial questions, from his projects, in which he will use this tactic. His initial list is the following:

1. Is the app's average loading time greater than expected?
1. How many alarms can be active at the same time?
1. How many times the user has had forgotten to take the medication?
1. Which features are being used less than 3 times a week?
1. Do we know if the user is already paying for an insurance service?
1. Can a psychologist be interested in what activities consider the users as bored?
1. Is the app colorful enough?
1. Which profile of people have the most accidents?

Sam takes the first question and starts talking about the question with Sam2.

### Question 1
>Is the app's average loading time greater than expected?

**Sam2:** can you give me a set of possible answers to this question?

**Sam:** Yes and No.

**Sam2:** Ok, Is a *yes*  useful for you?

**Sam:** Yes, because if the app takes in average more than the expected then it means that something is no working well and then we have to......

**Sam2:** OK, OK... stop there,... you are giving me a justification, this mean that you want to validate a hypotheses, aren't you?

**Sam:** no, why?

**Sam2:** well you are telling me that if your average loading time is greater than expected, then you have to take an action. What are your hypotheses there?,.. maybe it means that something is not working correctly.

**Sam:** mmm let me think, ok maybe I'm trying to validate that we have a good response time, that we are accomplishing a goal.

**Sam2:** Ok, then you should ask a question with that in mind. Let's give it another  a try.

**Sam:** Did we accomplishing  in the last week our goal of 2 seconds in average loading time or do we have to  do some changes to accomplish this?

**Sam2:** That is ok, you are giving a context, introducing your hypotheses with words like **accomplishing our goal of 2 seconds** and **or do we have to...**, remember that you can also use the question as it is, but you **must present** an example (like the examples in this book).

**Sam2:** Ok, now you have a question, can you tell me which type of question it is?

**Sam:** mm I'm not very sure, however .. I have a feeling that it is type 1.

**Sam2:** Yes! it is, You could use this as a guide: if you answer yes to some of these questions, you have a good probability that this questions is a type 1.

- Does the question involve any resources of the phone (memory usage, etc..)?
- Does the question refer to possible points of failure, bugs, errors, or crashes ?
- Is the data used for answering the questions internal (reports about the usage, information that you collected from the devices)?
- Will the answer not be presented to the final user ?

**Sam:** (answers)

- Does the question involve any resources of the phone (memory usage, etc..)? (yes)
- Does the question refer to possible points of failure, bugs, errors, or crashes ? (yes)
- Is the data used for answering the questions internal (reports about the usage, information that you collected from the devices)? (yes)
- Will the answer not be presented to the final user ? (yes)

**Sam:** Thanks Sam2!

### Question 2

> Second question: How many alarms can be active at the same time?

**Sam2:** Sam, this question has the same problem than the previous one, this question has only two possible answers Yes and NO. Are you going to validate a hypotheses?

**Sam:** No, this time I was not trying to validate or reject any hypotheses. After reading the question **out loud**, it makes neither sense to me.

**Sam2:** OK, then continue with the third question.

### Question 3

> Third question: How many times the user has had forgotten to take the medication?

**Sam:** well let me start with this, the question has as possible answers any positive number.

**Sam2:**  yes, you are right, you have a good question, Which type is it?

**Sam:**  With this one I'm really lost, I do not know.

**Sam2:** Well this is a type 2 question, if you notice most of the following questions are going to be answered with a yes.

- Does the question involve the context of the user?
- Does the question refer to personal information of the user?
- Does the question refer to information that is related to the user interactions with the app?
- Is the data used for answering the questions internal and could it be extended with external information?
- Will the answer be presented to the final user (as a reminder, notification, icon in the app, email,etc..)?
- Does the answer try to help/guide/remind to the user something?

**Sam:** (answers)

- Does the question involve the context of the user? (yes)
- Does the question refer to personal information of the user? (yes)
- Does the question refer to information that is related to the user interactions with the app? (yes)
- Is the data used for answering the questions internal and could it be extended with external information? (yes)
- Will the answer be presented to the final user (as a reminder, notification, icon in the app, email,etc..)? (yes)
- Does the answer try to help/guide/remind to the user something? (yes)

**Sam:** Oh, now I see, I notice that for this type of question the user is the center of the question, the answer is for her, am I wrong?

**Sam2:** No, you are right. This type of question is focused on how to help the user in the daily interaction with the app, how you can improve the interaction, how you can improve your UX by providing her with useful information/knowledge ..

### Question 4

> Fourth question: Which features are being used less than 3 times a week?

**Sam:**  This question has as answers a list of functionalities of the app. And I'm confused about whether it is type 2 or type 3.

**Sam2:** Ok, let's do this, Could you please answer these questions? 

- Does the question involve a time in which a functionality of the app has not being used?
- Does the question involve information about the competence (similar apps)?
- Does the answer have an impact in adding/removing/updating a feature/functionality?

**Sam:** (answers)

- Does the question involve a time in which a functionality of the app has not being used? (yes)
- Does the question involve information about the competence (similar apps)? (no)
- Does the answer have an impact in adding/removing/updating a feature/functionality? (yes)

**Sam2:** As you may see, you answered most the questions with a yes, when this happens there good chance of having a type 3 question.

**Sam:** ok, I see but when adding or removing a feature I can impact the user directly and it is something that the user will see directly in the app.

**Sam2:** Yes, you are right, however the main difference with the type 2 question is that, this question involves developing new functionalities or removing/updating some of them because they are deprecated or useless for the user. Furthermore, this type of question does not communicate the answer to the user as a part of the existing app, i.e., no information/knowledge is provided to the user via the app.

### Question 5

 > Fifth question: Do we know if the user is already paying for an insurance services?

**Sam:** Now I know that this is a yes/no question. I will reformulate it.... maybe like this: **How many users are not paying for an insurance services?**, I'm trying to gain some money here, this makes it a type 4 question?

**Sam2:** now that you reformulated your question, and it is a good business question then we can classify it. For this I have some questions for you, please answer them.

- Does the main purpose of this question involve making a profit?
- Does the question need to use as a data source the way in which your users interact with the app?
- Could the answer or related information be sold to third parties?
- Does the answer help you to put/locate some adds or publicity in your app?
- Did you have to investigate previously who (external person / group of people) would be interested in the answer?

**Sam:** (answers)

- Does the main purpose of this question involve making a profit? (yes)
- Does the question need to use as a data source the way in which your users interact with the app? (yes)
- Could the answer or related information be sold to third parties? (yes)
- Does the answer help you to put/locate some adds or publicity in your app? (no)
- Did you have to investigate previously who (external person / group of people) would be interested in the answer? (yes)

**Sam:** well, I can see that these questions   are related to external people, and I can get some money answering them.

**Sam2:** Yes, indeed. And in order to answer the question it  is required to collect information about how your user interacts with the app, thus, in this way you can spot interesting insights, such as the app parts where the users stay longer or  are frequently visited. You also have to investigate previously who would be interested in this information. Can you tell me how would be interested in the answer of your question?

**Sam:** Yes, the people who would love to have these information are the owners of the insurances companies. I could put some adds in the app or self anonymized information.

### Questions 6 and 7

**Sam2:** I'm seeing your question list. Let's group now questions 6 and 7. Can you guess why?

> Sixth question:  Can a psychologist be interested in what activities consider the users as bored?
> Seventh question: Is the app colorful enough?

**Sam:** Yes, these are not valid questions. For the first one, an analytics engine can not answer about an external person, like a psychologist, if it is interested or not in an information of our app. In the second question I have a subjective adjective **colorful enough**. Am I right?

**Sam2:**Yes, you are. Can you change the second question to be a valid one?, or can you make a guess how can you improve it?

**Sam:** mm maybe I can define what I meant with the phrase colorful enough, like it has at least three different colors.

**Sam2:** Yes, as you said **defining a metric for the subjective attributes** can help to clarify a question. However, in this case you have to formulate questions that are useful for you, the users or external people once it is on production.


### Question 8

> Eighth question: Which profile of people have the most accidents?

**Sam2:** What is the purpose of this question?

**Sam:** I want to sell the general profile, of the people who has more accidents, to insurance companies, and I want to recommend some extra safety measures to users directly in the app.

**Sam2:** So, you are trying to telling me that you are **mixing more than one objective of the previous types?**

**Sam:** yes, I want to make a profit (type 4), and also I want to improve the user experience with the app (type 2)
recommending some measures with an additional text in the app.

>As you may notice Sam and Sam2 had a conversation that involves the business questions Sam expected to answer, the purpose of it and also how Sam was going to present the answer (how and how). This is really important when you are formulating business questions, and one very useful way of validating the questions is by imagining your data twin.  
