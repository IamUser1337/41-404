Generative answers are a popular topic right now. Generative AI enables organizations to be able to provide more natural conversations to their customers. Generative answers in Copilot Studio allow your copilot to find and present information from multiple sources, internal or external, without created topics. Generative answers can be used as primary information sources or as an alternative source when authored topics can't answer a user's query. As a result, you can quickly create and deploy a functional copilot. You don't need to manually author multiple topics that might not address all customer questions.

When a copilot can't find a matching intent (topic) for the user's query, it can use generative answers and tries to answer a question. This behavior is called "Generative Answers for fallback." If the user's intent isn't matched to topics or generative answers, the fallback [system topic](/microsoft-copilot-studio/authoring-system-topics) is used. System topics can escalate a query for the copilot.

Generative answers aren't limited to fall back scenarios. Your copilot can also use other web sites, external or internal web sources, and knowledge sources such as SharePoint or OneDrive.

Generative answers can use these sources:

- External resources:

	- [Bing Web Search](/bing/search-apis/bing-web-search/overview)—doesn't require external configuration.

	- [Bing Custom Search](https://www.customsearch.ai/)—requires external configuration.

- Internal resources:

	- SharePoint

	- OneDrive

	- Documents uploaded to Dataverse

	- Custom data (internal or external): supply your own source, such as a Power Automate Flow or from Skill