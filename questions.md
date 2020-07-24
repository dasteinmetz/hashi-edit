# Questions for writer and keeper of standards

* Branding and legal: Do we require full product name on first mention, such as "HashiCorp Terraform allows ..."? Did not include in this revision. Also, apparently HashiCorp brands are not registered trademarks, at least not coming up on the Terms page and USPTO site. So assuming no need to add TM or R bugs.

* Revised the following sentence to avoid the marketing angle and flowery speech. Also, need to ensure that we can defend the statement. "Terraform is the most popular language for defining and provisioning infrastructure as code (IaC)." Also, wouldn't it be more accurate to talk about HashiCorp Configuration Language (HCL) in this case, instead of the Terraform product?

* As written, this guide targets Linux users who have installed Docker (at least that is my understanding). I've added text into the Prerequisites section to make this clear. Also, let's discuss whether the title or links to the guide can be clear about this focus as well. Perhaps in the future we can revise the exercise to target a broader audience. 

* This revised version includes more information about installation, including unzipping and verifying. However, it could be expanded on to be more helpful. Let me know what you think. We also might want to link out to troubleshooting pages for PATH.

* Added a sentence about confirmation after using the `terraform apply` command. 

* I attempted to test out the steps in this guide, but I was not able to complete all of them, probably due to mistakes on my part. Can you run through this again, based on the revision? Maybe we can share notes.

* For now, the links do not open in a new browser tab. Let's discuss whether that would make sense, such as for the download links.

* The template allows us to show steps using more than CLI commands; however, I assume that those options are not realistic for this guide. 

* This topic did not include a "Next steps" section. Is there content that would make sense here? Suggested content has been added for now Ideally, we could point to a specific guide or tutorial. 

* The Guide template shows sentence-style capitalization for subheads, including for "Next steps." However, published guides such as that for Nomad show title case for "Next Steps." Let's discuss this inconsistency between the two and determine a solution. 