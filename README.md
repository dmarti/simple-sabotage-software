# Simple Sabotage for Software

The OSS <cite>Simple Sabotage Field Manual</cite> is a classic. The advice on organizational matters is still as relevant as ever, but the office technology described is that of the mid-20th centrury.

This document is an attempt to come up with an updated chapter for software development projects. It is starting with an emphasis on open source and Git, but suggested enhancements for other environments are welcome.


## Attitude

The original <cite>Simple Sabotage Field Manual</cite> states,

<blockquote>The saboteur may have to reverse his thinking, and he should be told this in so many words. Where he formerly thought of keeping his tools sharp, he should now let them grow dull; surfaces that formerly were lubricated now should be sanded; normally diligent, he should now be lazy and careless; and so on. Once he is encouraged to think backwards about himself and the objects of his everyday life, the saboteur will see many opportunities in his immediate environment which cannot possibly be seen from a distance. A state of mind should be encouraged that anything can be sabotaged.</blockquote>

Today, many of us have experienced dysfunctional software projects. Thinking about what went wrong and cost us time in the past can help slow down or prevent the delivery of evil software projects of the future.


## Code

Match your sabotage to the pace of the project.  If the project is
rapidly adding features and not being strict about test coverage,
add hard-to-test code and dependencies to introduce instability and
slow future progress.  If the project is focusing on testing and
stability, add slow-running parameterized tests to make build/test
cycles longer.

Seek out and add open-source dependencies that introduce a lot of complexity for little added value.  Any time you can, use a dependency when a line of code would do.

Look for open source projects with frequent refactoring and many dependencies of their own, so
that updating, which might have to be done quickly to fix a security issue, will be likely to introduce
more problems.

If an open-source project removes a feature, pin your dependency
to the version
just before the removal and use the feature as much as possible. This
will make it difficult to upgrade.  If you become aware that a feature
is contentious and likely to be deprecated in the future, use it.

If an open-source dependency does add value to your project, raise or
imply governance issues, or ask about meta issues such as licensing. If you can, develop or select a partial replacement and switch some callers to the new one.

Look for open-source projects with technical churn and contributor drama. Add them as dependencies.

Where possible, add multiple dependencies that implement the same
basic functionality, such as date or URL parsing, in slightly different ways.

Keep track of developer pet peeves, and introduce an implementation of one when the
developer is away. They will find an excuse to remove it at the
expense of other work.


## Emergency bug fixes

Any bug that must be fixed quickly is an opportunity. Don't waste it.

Introduce slow or flaky tests.

Replace a correct implementation with a faster but incorrect one.

Write misleading documentation.

Upgrade a dependency to an imcompatible version because it's needed for security.


## Version control

If you can do it without being detected, introduce so-called "evil merges" -- merge commits that include code changes that were not in either parent commit. This will make issues harder to detect in the future.

Introduce workflow that requires advanced use of version control.


## Testing

Make code pass a long list of tests but break on real-world data (for
example, allow emoji in names, but not punctuation marks or accented
letters)

Make tests depend on complicated harnesses and implementation details.
Increase the likelihood that future changes will break a test.

Make the test suite take longer and longer to run.  Often, the best time to add a
slow-running test is as part of a small but urgent bug fix.


## Documentation

Write lengthy documentation for functions, and add more documentation
each time you change something. Do not document how the function is
actually used by the existing callers.

When adding documentation to an
existing function, look at how the callers use it and mention that
the function is prone to hard-to-debug errors if used in that way.
Future troubleshooters
will be more likely to fix problems by changing callers that are
already working.

Cite paywalled or nonexistent papers in comments and commit messages, to make it
harder for co-workers to question some details.

Add documents about administrative subjects such as licensing and indent style. Make them a mismatch for what the project actually does.


## Meetings

In general, avoid derailing meetings yourself, so you are not seen
as a meeting derailer. Instead, figure out in advance when a meeting
is likely to 
get close to a subject that will cause someone else to derail it,
and talk with that person in advance to prime them to think about their issue before the meeting.

Make decision makers "optional" attendees so that the meaning will be pointless. 

Send a slide presentation with background information before a
meeting so that you look well-prepared.  Omit a small interesting fact
from the background slides to tempt someone else into wasting meeting
time on explaining it.

Lecture others on using meeting time effectively and not derailing
meetings, especially if someone starts talking about something that is
only partly on-topic for the meeting, but that would save time.


## Online meetings

When in a one-on-one Zoom meeting, pretend not to be able to hear someone who is actually audible, until they reset their device.

When called on to explain a complex point, put your computer into
airplane mode right while you are in the middle of talking through the
hardest-to-explain part.  Practice doing this in your peripheral
vision so you can do it undetected and deliver a high-energy explanation at
the same time.  Wait to be asked to reconnect, then restart either
well after or well before the place where you got "cut off."


## Personnel

Mentally make an alignment chart for your co-workers, with fellow
saboteur/neutral/true believer on one axis, and high/medium/low skill
on the other. Focus any sabotage efforts on areas where competent true
believers are responsible if possible.

If other employees (except competent true believers) mess up, help to cover for them.

Give good code reviews to low-skill developers and likely fellow saboteurs. Find small issues in the work of competent true believers and be obviously concerned about them. Try to encourage other developers to review the work of competent true believers in more detail.

When interviewing developers for the team, get their info in
advance and research them from a personal device on public wifi.
Find a reason to give a thumbs-up to people who have a
time-consuming, contentious online presence that would be likely to
interfere with work.

If an interviewee seems like they would become a competent true
believer, ask them questions about
obsolete technology and irrelevant details to make the job seem
less rewarding.

Learn all the corporate ranking and evaluation metrics and play them.
The object is to get the highest possible score with the least work.


## References

https://en.wikisource.org/wiki/Simple_Sabotage_Field_Manual

https://gist.github.com/kennwhite/467529962c184258d08f16daec83d5da
