# Terminal chat bot using the OpenAI API

- Add environment vairable ```OPENAI_API_KEY``` to .env file with your OpenAI API key
- Update content key in chat.js file to describe the type of bot you want to interact with
```js
 content: {
      `You are a teacher of software development and I am your student.`,
  },
```
- Run ```node chat.js```

## Temperature Ranges 
Changing the temperature key can provide more creative or fact based answers depending on the setting. Changing the temperature can be done in ```chatCompletion``` within ```chat.js```.

```js
const chatCompletion = await openai.chat.completions.create({
    messages: [...history, message],
    model: 'gpt-3.5-turbo',
    temperature: 1.3,
  })
```
### Understanding Temperature in AI Models: (ChatGPT 4 description)
Low Temperature (e.g., 0 to 0.5): A lower temperature value makes the model's responses more deterministic and repetitive. At very low temperatures, the model is more likely to choose the most probable words or tokens at each step of the generation process. This can be useful when you want more predictable and conservative outputs.

Medium Temperature (e.g., 0.5 to 1.0): This is often considered a balanced range, where the model generates outputs that are neither too random nor too deterministic. It's a common default setting for many applications, aiming to strike a balance between creativity and coherence.

High Temperature (>1.0): Higher temperature values increase randomness, making the model's responses more diverse and potentially more creative or unexpected. However, too high a temperature can lead to outputs that are nonsensical or highly erratic.
