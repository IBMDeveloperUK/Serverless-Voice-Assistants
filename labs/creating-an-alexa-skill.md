# Creating an Amazon Alexa Skill

### Background

[Alexa](https://developer.amazon.com/alexa) is Amazon's cloud-based voice service. Most people are familiar with the service through using an [Amazon Echo or Echo dot](https://developer.amazon.com/alexa/echo) but the service can also be integrated in to custom internet-connected devices like this talking robotic fish:
[![IMAGE ALT TEXT HERE](https://img.youtube.com/vi/bRxhgxH6FUI/0.jpg)](https://www.youtube.com/watch?v=bRxhgxH6FUI)

### Creating the action

#### Listing the random buzzwords

To create a random corporate strategy each time we're going to break the statement in to five parts; a **prefix**, an **adverb**, a **verb**, an **adjective** and a **noun**. Strung together in this order we should be able to create a reasonable sounding meaningless statement of strategy.

1. Create a new empty JavaScript and name it 'generator.js'.

2. Add an array of prefixes to the top of the file:

```javascript
const prefixes = new Array(
    'We need to', 'It would be best if we could', 'We can obtain growth if we', 'Our strategy is to', 'The company is striving to',
    'We are on a journey to', 'We should', 'Our employees are working to', 'Our company has a clear strategy which is to',
    'Our organisation is striving to', 'We have committed to', 'We have a strong policy which is to', 'Our long-term goal is to',
    'In the short-term we will'
);
```

3. Beneath this variable create a variable for our adverbs:

```javascript
const adverbs = new Array(
    'appropriately', 'assertively', 'authoritatively', 'collaboratively', 'compellingly', 'competently', 'completely',
    'continually', 'conveniently', 'credibly', 'distinctively', 'dramatically', 'dynamically', 'efficiently',
    'energistically', 'enthusiastically', 'globally', 'holisticly', 'interactively', 'intrinsically', 'monotonectally',
    'objectively', 'phosfluorescently', 'proactively', 'professionally', 'progressively', 'quickly', 'rapidiously',
    'seamlessly', 'synergistically', 'uniquely', 'fungibly'
);
```

4. Add another variable below that for our verbs:

```javascript
const verbs = new Array(
    'actualize', 'administrate', 'aggregate', 'architect', 'benchmark', 'brand', 'build', 'communicate', 'conceptualize',
    'coordinate', 'create', 'cultivate', 'customize', 'deliver', 'deploy', 'develop', 'disintermediate', 'disseminate',
    'drive', 'embrace', 'e-enable', 'empower', 'enable', 'engage', 'engineer', 'enhance', 'envisioneer', 'evisculate',
    'evolve', 'expedite', 'exploit', 'extend', 'fabricate', 'facilitate', 'fashion', 'formulate', 'foster', 'generate',
    'grow', 'harness', 'impact', 'implement', 'incentivize', 'incubate', 'initiate', 'innovate', 'integrate', 'iterate',
    'leverage existing', 'leverage other\'s', 'maintain', 'matrix', 'maximize', 'mesh', 'monetize', 'morph', 'myocardinate',
    'negotiate', 'network', 'optimize', 'orchestrate', 'parallel task', 'plagiarize', 'pontificate', 'predominate',
    'procrastinate', 'productivate', 'productize', 'promote', 'provide access to', 'pursue', 'recaptiualize',
    'reconceptualize', 'redefine', 're-engineer', 'reintermediate', 'reinvent', 'repurpose', 'restore', 'revolutionize',
    'scale', 'seize', 'simplify', 'strategize', 'streamline', 'supply', 'syndicate', 'synergize', 'synthesize', 'target',
    'transform', 'transition', 'underwhelm', 'unleash', 'utilize', 'visualize', 'whiteboard', 'cloudify', 'right-shore'
);
```

5. After that add our list of adjectives:

```javascript
const adjectives = new Array(
    '24/7', '24/365', 'accurate', 'adaptive', 'alternative', 'an expanded array of', 'B2B', 'B2C', 'backend',
    'backward-compatible', 'best-of-breed', 'bleeding-edge', 'bricks-and-clicks', 'business', 'clicks-and-mortar',
    'client-based', 'client-centered', 'client-centric', 'client-focused', 'collaborative', 'compelling', 'competitive',
    'cooperative', 'corporate', 'cost effective', 'covalent', 'cross functional', 'cross-media', 'cross-platform',
    'cross-unit', 'customer directed', 'customized', 'cutting-edge', 'distinctive', 'distributed', 'diverse', 'dynamic',
    'e-business', 'economically sound', 'effective', 'efficient', 'emerging', 'empowered', 'enabled', 'end-to-end',
    'enterprise', 'enterprise-wide', 'equity invested', 'error-free', 'ethical', 'excellent', 'exceptional', 'extensible',
    'extensive', 'flexible', 'focused', 'frictionless', 'front-end', 'fully researched', 'fully tested', 'functional',
    'functionalized', 'future-proof', 'global', 'go forward', 'goal-oriented', 'granular', 'high standards in',
    'high-payoff', 'high-quality', 'highly efficient', 'holistic', 'impactful', 'inexpensive', 'innovative',
    'installed base', 'integrated', 'interactive', 'interdependent', 'intermandated', 'interoperable', 'intuitive',
    'just in time', 'leading-edge', 'leveraged', 'long-term high-impact', 'low-risk high-yield', 'magnetic',
    'maintainable', 'market positioning', 'market-driven', 'mission-critical', 'multidisciplinary', 'multifunctional',
    'multimedia based', 'next-generation', 'one-to-one', 'open-source', 'optimal', 'orthogonal', 'out-of-the-box',
    'pandemic', 'parallel', 'performance based', 'plug-and-play', 'premier', 'premium', 'principle-centered', 'proactive',
    'process-centric', 'professional', 'progressive', 'prospective', 'quality', 'real-time', 'reliable', 'resource-sucking',
    'resource-maximizing', 'resource-leveling', 'revolutionary', 'robust', 'scalable', 'seamless', 'stand-alone',
    'standardized', 'standards compliant', 'state of the art', 'sticky', 'strategic', 'superior', 'sustainable',
    'synergistic', 'tactical', 'team building', 'team driven', 'technically sound', 'timely', 'top-line', 'transparent',
    'turnkey', 'ubiquitous', 'unique', 'user-centric', 'user friendly', 'value-added', 'vertical', 'viral', 'virtual',
    'visionary', 'web-enabled', 'wireless', 'world-class', 'worldwide', 'fungible', 'cloud-ready', 'elastic', 'hyper-scale',
    'on-demand', 'cloud-based', 'cloud-centric', 'cloudified', 'agile'
);
```

6. Finally add our array of nouns:

```javascript
const nouns = new Array(
    'action items', 'alignments', 'applications', 'architectures', 'bandwidth', 'benefits',
    'best practices', 'catalysts for change', 'channels', 'collaboration and idea-sharing', 'communities', 'content',
    'convergence', 'core competencies', 'customer service', 'data', 'deliverables', 'e-business', 'e-commerce', 'e-markets',
    'e-tailers', 'e-services', 'experiences', 'expertise', 'functionalities', 'growth strategies', 'human capital',
    'ideas', 'imperatives', 'infomediaries', 'information', 'infrastructures', 'initiatives', 'innovation',
    'intellectual capital', 'interfaces', 'internal or "organic" sources', 'leadership', 'leadership skills',
    'manufactured products', 'markets', 'materials', 'meta-services', 'methodologies', 'methods of empowerment', 'metrics',
    'mindshare', 'models', 'networks', 'niches', 'niche markets', 'opportunities', '"outside the box" thinking', 'outsourcing',
    'paradigms', 'partnerships', 'platforms', 'portals', 'potentialities', 'process improvements', 'processes', 'products',
    'quality vectors', 'relationships', 'resources', 'results', 'ROI', 'scenarios', 'schemas', 'services', 'solutions',
    'sources', 'strategic theme areas', 'supply chains', 'synergy', 'systems', 'technologies', 'technology',
    'testing procedures', 'total linkage', 'users', 'value', 'vortals', 'web-readiness', 'web services', 'fungibility',
    'clouds', 'nosql', 'storage', 'virtualization', 'scrums', 'sprints', 'wins'
);
```

We now have all the data we need to create our strategies in our javascript file.

#### Picking from the array at random

To build our sentence we need to pick one element from each of these arrays randomly and add them together.

1. Add the following function to your JavaScript file:

```javascript
function returnRandomElement(arr) {
    var rand = arr[Math.floor(Math.random() * arr.length)];
    return rand;
}
```

We can pass an array of any size in to this function and it will return a random element from the array. Perfect!

#### Fixing the capitals

Some of the arrays have capitalised words and some do not. Let's fix that with a quick function.

1. Add this function to your file:

```javascript
function toTitleCase(str) {
    return str.replace(/\w\S*/g, function(txt) {
        return txt.charAt(0).toUpperCase() + txt.substr(1).toLowerCase();
    });
}
```

This function will capitalise the first letter of every word which should help keep our results consistent as well as add more drama to our corporate waffle!

#### Putting it all together

Finally we need to assemble our sentence. As we learned earlier, OpenWhisk looks for a `main()` function inside our file unless we explicitly specify a different entry point. We also need to return a JSON object to the platform.

1. Add the following `main()` function to your file and save it:

```javascript
function main() {

    var statement = returnRandomElement(prefixes) +
        " " + returnRandomElement(adverbs) +
        " " + returnRandomElement(verbs) +
        " " + returnRandomElement(adjectives) +
        " " + returnRandomElement(nouns);

    var response = {
        "text": statement
    }

    return response;
}
```

**Our action is ready. Lets upload it and invoke it to see it in action.**

2. Upload your file to IBMCloud Functions:

```
$ ibmcloud wsk action create generateStrategy generator.js
ok: created action generateStrategy
```

3. Test your action by invoking it from the CLI:

```
$ ibmcloud wsk action invoke -r generateStrategy
{
    "text": "We need to holisticly conceptualize client-focused value"
}
```

Try invoking it a few times to see the different results you get.

🎉🎉🎉 **Good job, your functionality is all ready to go. Now lets move on to integrating this with some voice assistants.** 🎉🎉🎉

### Next Lab:
[Creating an Amazon Alexa Skill](/labs/creating-an-alexa-skill.md)