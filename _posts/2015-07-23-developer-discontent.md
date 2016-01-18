---
layout: post
title:  "Fulfillment and Building X-Wings"
subtitle: "a theory of work and developer discontent"
date:   2015-07-23 19:22:19
categories: [work]
---
A recent feeling of burnout and subsequent conversations with colleagues and peers has got me thinking about developer discontent. Specifically, what makes developers happy, and what can organizations do to ensure that their dev teams are content and productive?

I have a theory, or perhaps more of a hypothesis. It’s untested, unsubstantiated and drawn out from anecdotal evidence. But right now, it feels to me like a truth that’s slowly dawning, making itself known on all fronts. It goes something like this:

1. Developers are sad when they can’t own their work.

2. Developers can’t own their work when they don’t know the people they’re doing it for.

3. Developers who are connected to their users are happier and more productive, and the products they make are more fully realized.

&nbsp;

----------


There’s a common misperception floating around about developers. This stereotype — I’ll call it the ‘problem solver’ myth — assumes that devs enjoy solving problems, full stop. Provide them with a list of requirements and constraints, give them the freedom to implement how they choose, and they will be happy.

This idea distills the ingredients for a Happy Dev Cocktail down to two:

1. Freedom of implementation

2. Clear articulation of requirements

The ‘problem solver’ myth is enticing because it comes close to the truth. Developers do love solving problems, and they do hate micromanagement. But I would argue that subscribing to this reductive stereotype demeans their creativity and ultimately results in sadder, less-productive devs and an incomplete product.

So, what is the missing ingredient?

Talking to developers and engineers throughout my (albeit short) career, I have yet to meet a true example of the ‘problem solver’ type. I know people who fit this bill exist, but they’re far less common in the startup world. As my colleagues and I sit down to pair in the morning, we warm up with articles on Hacker News. The questions we ask each other are rarely “how would you solve this problem?” and more often “would you ever start your own company?”

Yes, a technical problem is an engaging puzzle, but it’s just that — a puzzle. Nobody comes away from a jigsaw puzzle with a feeling that the work they’ve done is meaningful, lasting, or truly their own.

You will never achieve a lasting happiness with your work unless you can own that work, invest yourself in it, and breathe life into it directly from ideation to release. Moreover, work can’t be very meaningful unless the worker is connected to the person for whom they are working.

This is what managers, and I think many developers themselves, do not realize. Replicating a wireframe is about as fulfilling as building a Lego X-Wing. Exciting at first, but ultimately not meaningful. You put the finished product on a shelf and let it gather dust.

![awesome giant lego x-wing]({{ site.baseurl }}/assets/images/x_wing.jpeg)

Instead, rethink the way you build Legos. Rip open the box and throw away the manual. Forget what you thought you knew about an X-Wing. Call up Luke Skywalker and let him explain what he wants.

----------

Talk to a [Lean expert](https://en.wikipedia.org/wiki/Lean_manufacturing), and they will tell you all about “going to the gemba”. Gemba (現場) is a Japanese word that translates rather directly to “the real place”, that is, the place where the action happens. For an executive at Toyota Manufacturing, the gemba is the factory floor. According to the Toyota Production System (aka Lean), managers need to get as close to the gemba as possible. Theories and speculations and business models and projections are only as good as the work that gets done there.

If the Toyota executives could have been in the passenger seat of every vehicle as it left the sales floor, they would have. Well, guess what? We’re not building cars, we’re building software. And that makes getting to the gemba much easier.

Realistically, software can be made by teams of two or three developers in constant contact with their end users. It can be developed iteratively and remade in direct response to customer feedback. The entire thing can be built in a living room, or a garage, or a coffee shop.

The point isn’t that you should move your developer team into your parents’ attic. It’s that organizational structures in which developers, product designers and marketers exist in distinct silos are harmful and unnecessary. By design, this isolates the people making the product from those using it.

Separation from the gemba is also the reason why product-tech meetings can be so painful. It can be extremely frustrating for a dev to be handed a product requirement without understanding the surrounding context for why it matters, and more importantly, why it is meaningful to someone. Similarly, for a product person who understands that meaning, it can be frustrating when developers randomly strike out against the requirement.

Lack of a shared context for product development makes meetings which should be productive feel like a waste of time. We wouldn’t have this problem if everyone went to the gemba together.

Here’s the moral of the story: A project only has meaning when you can empathize with the person(s) who use it. Think about the last piece of software you built that held real meaning to you. Who uses it? Likely yourself, your loved ones, or your friends.

----------

You’re a project manager at a growing tech company. Every day, team members come to you with new complaints. Some of them are direct, concrete:

> Fred is micromanaging and won’t let me do my job.

Others are more ephemeral:

> I’m not proud of the work I’m doing here.

> I feel disconnected from our users.

> I’m burning out.

If you try to assume a direct cause for your team members’ unhappiness, you’re bound to fail. The answer to “Fred is micromanaging” is not “make Fred stop that.” Ask yourself Five Whys:

1. Why are developers unhappy? Because Fred is micromanaging.

2. Why is Fred micromanaging? Because he’s worried about implementation details.

3. Why is he worried about implementation details? Because he feels developers don’t share his concerns about the product.

4. Why do developers lack a shared vision with product? Because only product has interacted directly with the users.

5. Why haven’t developers interacted with the users?

That last one, you’ll have to answer yourself. If your developers are in a silo, your company is doing something wrong. Get them to the gemba, let them own the project, and everyone will be happier.

In fact, not only will your team be happier, but the product itself will be closer to the people that use it. And perhaps something entirely different will emerge. Just look at what happened with Basecamp — the company gave their remote developer in Denmark the freedom to own his project, and the result was not only a successful product, but one of the most popular web development frameworks in the world as well.

&nbsp;

----------


How do you accomplish this? If your organization is structured traditionally, with a product/UI team and a large team of developers directly under it, consider restructuring. Split up into teams of 3–4 employees per project, no more. Each member will feel like they own their area of the product, and getting to the real place will be that much easier.

There are real benefits to smaller team sizes. Less time will have to be devoted to explanations and long, painful meetings between product and tech. Team members will become cross-functional; the smaller size of the team will necessitate product and tech working closely together. Designers and developers will [learn how to satisfy one another’s needs](https://medium.com/facebook-design/how-not-to-make-your-engineer-s-life-completely-terrible-292a6d5d134c) without friction.

Moreover, the modularity of your product will improve. If your events system is owned and managed by a small team, other areas of the product will be less reliant on it; a catastrophic failure in that section won’t bring the whole thing down. Engineers know the strengths of separating out concerns within a codebase. Doing the same thing within an organization could yield similarly.

This is obviously a big change, but you can start small. Identify an area of your product that is suffering and could benefit from ownership. Pluck two or three devs and one product person who have displayed entrepreneurial qualities. Pluck them from whatever larger team they’re on, and hand them the reins.

It’s a bit of a radical experiment, and it carries risks. Developers may even shy away from the change at first. But if a company never modifies its process, that process can never get better. Continuous self-improvement is impossible without a bit of a risk.
