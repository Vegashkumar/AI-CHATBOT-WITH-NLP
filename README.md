**COMPANY** : CODETECH
**NAME** : VEGASH KUMAR M
**INTERN ID** : CA/JA1/5093
**DOMAIN** : PYTHON PROGRAMMING INTERNSHIP
**BATCH DURATION** : 1st January 2025 to 30th January 2025
**MENTOR NAME** : NEELA SANTHOSH
### Initialize trainer
```
trainer = cbv.modelTrain()
intents = trainer.loadIntents('intents.json')  # The path where the intents.json file is saved
words, classes = trainer.preprocess_save_Data(intents)  # Prepares and saves preprocessed word data
train_x, train_y = trainer.prepareTrainingData(words, classes)  # Prepares training data
```

### Create the model
`model = trainer.createModel(train_x, train_y, save_path='cbv_model.model')`

### Initialize predictor
`predictor = cbv.modelPredict('intents.json', 'cbv_model.model')`

### Get output from the bot
```
running = True
while running:
    msg = input('You: ')
    if msg == 'quit':
        running = False
    else:
        response = predictor.chatbot_response(msg)
        print('Bot: ', response)
```
