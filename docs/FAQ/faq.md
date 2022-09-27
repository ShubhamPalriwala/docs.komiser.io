# FAQs

## What's the difference between Oraculi and Komiser?

Komiser is the open-source version of [Oraculi](https://www.oraculi.io/). To get a more in-depth description of what Komiser is, read it [here](/docs/Introduction/what-is-komiser.md). In short, Komiser is a tool that prioritizes cloud transparency regarding the cost of your cloud resources. That's why komiser makes it easy to track all the resources and costs related to them, cross regions, and cross accounts. 

Oraculi on the other hand aims to be a more all-in-one DevOps tool. Oraculi is built for Developers, CTOs, and Project Managers not only DevOps engineers. 

Oraculi incorporates the Komiser cloud cost transparency features, along with security, governance features, and the ability to build custom dashboards on top of that. In addition with Oraculi the user will get a consolidated view of all their cloud resources cross-account and cross-cloud-provider through the `Inventory page`. 

Oraculi was established in late June 2022 and has a very ambitious feature roadmap that the team is working hard to deliver. So if an easy and accessible all-in-one cloud tool is something that could be valuable to you take a look at the [roadmap](https://oraculi.canny.io/) (or even consider adding to it) and [join us](https://discord.oraculi.io) for the ride. 

## What can Komiser help me with? 

Anybody who was ever tasked with managing a cloud provider account (that isn't a personal test account) understands how `painful` it is to track all the resources, cost, and security that goes along with it. Let alone managing multiple accounts, and let's not even get started about `multi-cloud` environments. 

Cloud providers for the most part are excellent, but they all have pretty `crummy web consoles`. Komiser brings **transparency** around what you have provisioned in your account and the cost it's incurring. You can toggle between cloud accounts and regions to uncover potentially **hidden costs**. Komiser brings to the **forefront** what was **hidden in the shadows**. 

## Is Komiser regularly maintained?

Komiser is an open-source project that is actively maintained by the Oraculi team. The tool is currently undergoing a complete frontend revamp which will bring new functionalities coming near the end of October 2022. Join the [Discord server](https://discord.oraculi.io) so you don't miss any updates.

## What is the dashboard data refresh rate?

Komiser and Oraculi consume the public cloud provider service APIs. So the refresh interval of the data visible in the dashboard is dependent on the cloud provider API refresh rate. For most service APIs in most cloud providers, the refresh rate is every `30 minutes`. We have gone to great lengths to ensure we do not cause any additional costs for your cloud account (including AWS, GCP and Azure), regardless of scale.

## Is it easy to migrate from Komiser to Oraculi?

Yes, the migration process is very easy. Just open an Oraculi account and link your cloud account credentials.

## How can I use tags?


**Oraculi tags**

On Oraculi you can add in the Inventory section. Choose the resource you would like to tag and click in the three dots (...) under `Actions` and then fill in the pop-up.

![add-tags](/img/add-tags.png)

**Cloud provider tags**

If you have resources tagged already in your cloud provider you will shortly to able to see those tags in the Komiser dashboard. You will be able to not only filter the tags you add on Komiser but also the tags configured in the cloud provider. 

**Komiser tags** 

Komiser will have the tagging feature delivered as part of the Komsier revamps efforts and will be delivered at the end of October as part of the Komiser v3.0.0 release. 

## How can I request a new feature?

If you would like to request a feature to be added to Komiser, feel free to do so through any of the following channels: 
- GitHub [issues](https://github.com/HelloOraculi/komiser/issues)
- Discord [server](https://discord.oraculi.io) (#feature-requests channel)
- During weekly Oraculi Office House, book a slot [here](https://calendly.com/jake-oraculi). 
- Via [Twitter](https://twitter.com/HelloOraculi) 
- Directly through our [Public Roadmap](https://roadmap.oraculi.io/komiser)

## Where can I see the upcoming features?

Keep tabs on what we are working on by bookmarking our [public roadmap](https://oraculi.canny.io/). We are aware that we have to always stay nimble and agile so if you think we should prioritize a certain feature over another, let your voice be heard by upvoting it, we really appreciate your input. Also, let us know if we are missing anything. 

## Does Komiser have access to my cloud data?

Since Komiser is completely self-hosted, Oraculi has zero access to any of your cloud data or personal information. 

## How can I build a custom dashboard? 

`Custom dashboards` are one of the main features we are working to deliver as soon as possible. We are very excited about being able to give users the chance to build customized dashboards filtering by certain regions, resources, or more importantly by `custom tags` to bring the clearest view to what you want to see. 

It will be available as an Oraculi feature at first and might be added to Komiser down the line. Once the feature is live we will announce it on Discord. If you don't have one already, we invite you to open a free-trial Oraculi account and test it out.

Still got questions? Speak to us directly on [Discord](https://discord.oraculi.io)! 

## How can I stay in the loop with new releases?

Head on over to our [changelog](https://www.oraculi.io/changelog). The best way to find out about the cool features and improvements we've shipped in the latest releases.