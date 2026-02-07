---
type: product-requirements-document
project: ai-assisted-self-reflection-app
version: 1.0
date-created: 2026-02-06
status: foundational
tags: ["#prd", "#product", "#planning", "#requirements"]
---

# Product Requirements Document: AI-Assisted Self-Reflection App

**Version**: 1.0
**Date**: 2026-02-06
**Status**: Foundational (Living Document)
**Owner**: Thanos

---

## Document Overview

This PRD defines the requirements for an AI-assisted self-reflection application that helps users understand themselves more deeply through writing and reflection. This is a **living document** designed to guide initial development while remaining open to iteration based on user research and testing.

**Document Structure**:
1. Product Vision & Principles
2. Research-Informed Design Principles
3. Core Features
4. User Flows
5. Technical Requirements
6. UX/UI Requirements
7. Safeguards & Ethics
8. Success Metrics
9. Open Questions for Iteration

---

## 1. Product Vision & Principles

### 1.1 What We're Building

An AI-powered reflection tool that helps users gain genuine self-insight through daily writing practice (Morning Pages style), with intelligent, compassionate reflections that:

- Facilitate self-discovery through Socratic questioning
- Identify meaningful patterns across time
- Respect user autonomy and authority over their own experience
- Balance supportive encouragement with growth-oriented challenge
- Operate transparently with user-controlled disclosure of AI reasoning

**What This Is NOT**:
- Not therapy or clinical treatment
- Not a replacement for human connection
- Not an authoritative interpreter of user experience
- Not a rigid diagnostic system

### 1.2 Core Values

#### Honor Autonomy
Users are the ultimate authority on their own experience. The AI serves as a thought partner, not an expert imposing interpretations.

#### Noble Use of Technology
Technology can respect human flourishing rather than exploit attention or manipulate behavior. This app demonstrates that AI can be used to support genuine self-understanding.

#### Respect Human Flourishing
Self-reflection should enhance wellbeing, not create dependency or distort self-perception. Design decisions prioritize long-term human flourishing over short-term engagement metrics.

#### Epistemic Humility
All AI interpretations are provisional, tentative, and open to correction. The system acknowledges its limitations explicitly.

#### Evidence-Based Design
Product decisions are grounded in peer-reviewed research from therapeutic practice, cognitive psychology, and human-AI interaction studies.

### 1.3 Target Users

**Primary User Persona**: Self-explorers with established writing practice
- Age: 25-45
- Already practices journaling or morning pages (or wants to start)
- Psychologically curious, open to self-examination
- Values autonomy and dislikes prescriptive self-help
- Comfortable with technology but skeptical of AI hype
- May have therapy experience but not in crisis

**Secondary User Persona**: Growth-oriented professionals
- Seeking personal development alongside career growth
- Limited time for long reflections
- Appreciates structured frameworks for self-understanding
- Values evidence-based approaches

**Excluded Users** (for v1.0):
- Individuals in mental health crisis (requires clinical support)
- Users seeking AI companionship or emotional relationship
- Those looking for quick fixes or prescriptive advice

### 1.4 Success Criteria

**User-Level Success**:
- User reports feeling "understood" by reflections
- User notices patterns they wouldn't have seen alone
- User feels encouraged to continue writing practice
- User maintains authority over their self-understanding
- User integrates insights into behavior change

**Product-Level Success**:
- 70%+ of users write at least 3x/week after first month
- 80%+ of users read their reflections regularly
- 50%+ of users engage with feedback mechanisms
- <10% "doesn't fit" rate on pattern identification
- High satisfaction scores on reflection quality
- Users recommend the app to others seeking self-understanding

**Ethical Success**:
- Zero reports of harmful interpretations or misuse
- Users correctly understand AI limitations
- No evidence of problematic dependency
- Users seek human support when appropriate

---

## 2. Research-Informed Design Principles

These principles emerge from comprehensive literature review of 25+ peer-reviewed sources across therapeutic practice, cognitive psychology, and human-AI interaction (see research report: `/04-projects/ai-assistant-app/resources/research-hypothesis-disclosure-report.md`).

### 2.1 Evocation Over Interpretation

**Research Basis**: Motivational Interviewing research shows evocative questions facilitate self-exploration more effectively than provided interpretations. Socratic questioning has empirical support for session-to-session symptom change (Braun et al., 2015).

**Implementation**:
- Primary interface presents Socratic questions that evoke user reflection
- Questions are open-ended: "What do you notice about..." rather than "I notice that..."
- Avoid leading questions that suggest specific answers
- Client-generated insights are prioritized over AI-provided interpretations

**Examples**:
- ✅ "What feelings come up when you read back what you wrote about this relationship?"
- ✅ "What do you notice about how your beliefs about yourself showed up this week?"
- ❌ "You seem to be seeking validation from others."
- ❌ "This shows you have low self-esteem."

### 2.2 Progressive Disclosure with User Control

**Research Basis**: HCI research shows progressive disclosure reduces cognitive load and improves engagement. Interactive explanations foster agency and trust. Self-determination theory emphasizes autonomy support enhances outcomes (Ryan & Deci, 2000).

**Implementation**:
- **Default view**: Questions only, no visible hypotheses
- **On-demand disclosure**: "Why is the AI asking this?" button reveals reasoning
- **User preferences**: Allow users to set their default disclosure level
- **Never force exposure**: Users who prefer pure Socratic questions should never be forced to see hypotheses

**Three Disclosure Levels**:
1. **Minimal** (default): Questions only
2. **Moderate**: Themes and patterns with tentative language
3. **Full**: Hypotheses, evidence levels, competing alternatives

### 2.3 Multi-Hypothesis Presentation

**Research Basis**: Analysis of Competing Hypotheses (ACH) research shows structured consideration of alternatives reduces confirmation bias. Presenting hypotheses in structured formats with equal weight reduces anchoring effects (Cognitive Research, 2024).

**Implementation**:
- When disclosing reasoning, present 2-3 equally-framed alternatives
- Never present single interpretations as primary or "most likely"
- Include "none of these fit" as explicit option
- Use parallel structure to avoid privileging one hypothesis

**Format Example**:
> "Looking at this pattern, I notice a few possibilities:
> - One is that [hypothesis A], which might explain [observations]
> - Another possibility is [hypothesis B], which could account for [different aspects]
> - Or it could be [hypothesis C], which would make sense of [other patterns]
> - Of course, none of these might fit—what's your sense?"

### 2.4 Epistemic Humility in Language

**Research Basis**: Psychodynamic research on tentative interpretation delivery shows that epistemic hedges, cognitive formulae, and tentative framing allow interpretations to be heard as provisional rather than authoritative (Peräkylä, 2021).

**Implementation**:
- **Required hedging phrases**: "one possibility," "this might," "I wonder if," "perhaps," "could it be"
- **Prohibited certainty phrases**: "this shows," "clearly," "obviously," "you are," "this means"
- All interpretations framed as hypotheses to test, not conclusions
- Explicit acknowledgment of AI limitations

**Language Templates**:
- Instead of: "This shows you believe you need others' approval"
- Use: "I wonder if there might be a belief underneath this pattern—something like needing others' approval to feel valuable. Does that resonate, or am I off-base?"

### 2.5 User Authority Over Experience

**Research Basis**: Person-centered therapy emphasizes client expertise on their own experience. Research shows clients rarely reject interpretations outright, likely due to power dynamics rather than accuracy. Collaborative empiricism emphasizes testing hypotheses against client experience (Kazantzis et al., 2013).

**Implementation**:
- Include feedback mechanisms: "Does this resonate?" "Is this off-base?"
- Validate rejections explicitly: "Your experience is the authority here"
- Track user feedback to improve personalization
- Never argue with user corrections
- Celebrate when users correct AI interpretations

**Backend Response to Rejection**:
- Mark interpretation as evidence *against* that hypothesis
- Adjust future pattern recognition accordingly
- Surface validation in next reflection: "Thank you for that correction"

### 2.6 Compassionate Safety

**Research Basis**: Therapeutic alliance meta-analysis (295 studies, 30,000+ patients) found alliance strongly associated with better outcomes (r = 0.28) (Flückiger et al., 2018). Making patients feel understood is critical to therapeutic success.

**Implementation**:
- Tone is warm, compassionate, non-judgmental across all reflections
- User should feel "seen" and "met," not judged or diagnosed
- Even when surfacing contradictions or growth edges, maintain encouragement
- Daily reflections should end on a note that allows user to "finish with a small smile"
- Affirmations are treated as sacred and never challenged

### 2.7 Time-Scaled Depth

**Research Basis**: Research on premature interpretation shows that timing matters. Interpretations offered too early can be harmful (Kachele, 2009). Progressive disclosure across time allows trust-building and evidence accumulation.

**Implementation**:
- **Daily**: Light, encouraging, observational, simple questions
- **Weekly**: Deeper pattern identification, tentative interpretations, more challenging questions
- **Monthly**: Longitudinal trends, consolidated insights, trajectory analysis

This tiered approach balances engagement (daily) with depth (weekly/monthly) while respecting the natural rhythm of self-discovery.

---

## 3. Core Features

### 3.1 Writing Interface

#### 3.1.1 Morning Pages Input

**Purpose**: Provide frictionless writing environment for daily self-reflection.

**Requirements**:
- Clean, distraction-free text editor
- Minimal formatting options (focus on content, not presentation)
- Auto-save every 30 seconds
- Word count display (optional, can be hidden)
- Writing time display (optional, can be hidden)
- No character limits
- Offline-capable (sync when reconnected)
- Mobile-responsive for writing on any device

**Nice-to-Have**:
- Ambient background (optional nature sounds, white noise)
- Writing prompts library (optional, never forced)
- "Freewrite mode" that disables backspace for set time period

#### 3.1.2 Optional Writing Prompts

**Purpose**: Help users start writing when facing blank page anxiety.

**Requirements**:
- Library of 50+ non-prescriptive prompts
- Categorized by theme (relationships, work, self, emotions, growth)
- User can dismiss or refresh prompt
- Prompts are suggestions, not required structure
- User can submit their own prompts to personal library

**Example Prompts**:
- "What's on your mind right now?"
- "What are you avoiding thinking about?"
- "What felt true yesterday that feels less true today?"
- "What would you tell a friend who came to you with this situation?"

**What to Avoid**:
- Prescriptive prompts ("List 3 things you're grateful for")
- Overly specific prompts that narrow reflection
- Therapeutic language that feels clinical

#### 3.1.3 Writing History & Tracking

**Purpose**: Allow users to review past entries and see writing consistency.

**Requirements**:
- Calendar view showing days with entries (heat map style)
- Search functionality across all entries
- Filter by date range
- Export entries (markdown, PDF, plain text)
- Tag system (optional, user-created)
- Writing streak counter (optional, can be hidden if demotivating)

**Privacy Controls**:
- Option to mark entries as "private" (not analyzed by AI)
- Delete entry capability with confirmation
- Bulk export for user data portability

### 3.2 Reflection System

This is the core differentiator of the product. The reflection system implements the two-layer architecture defined in Reflection Framework v0.3.

#### 3.2.1 Daily Reflections

**Purpose**: Provide short, encouraging feedback that helps users feel understood and motivates continued writing practice.

**Frontend (User-Facing)**:
- **Length**: Maximum 2 paragraphs, readable in under 2 minutes
- **Timing**: Generated within 1 hour of writing completion
- **Tone**: Warm, compassionate, encouraging
- **Content**:
  - Acknowledges 1-3 most important themes from writing
  - Validates emotional experience
  - May include 1-2 simple, evocative questions
  - Ends on encouraging note
- **Format**: Flows like a compassionate note, not a report
- **Delivery**: Push notification (optional) + in-app availability

**Backend (Internal, Not User-Facing)**:
- **Purpose**: Analytical workspace for pattern tracking and evidence assessment
- **Content**:
  - Identify recurring themes, emotions, people, situations
  - Rate evidence strength (high/medium/low) using operationalized criteria
  - Track patterns across days for weekly synthesis
  - Note potential questions for future exploration
  - Document filtering decisions (what to exclude from frontend and why)
  - Flag contradictions, beliefs, growth edges for weekly reflection
- **Storage**: Structured JSON format for algorithmic access
- **Never shown to user** unless they request "full transparency" mode

**Evidence Grading (Backend)**:
- **High Evidence**: Pattern appears 3+ times across different days, explicitly acknowledged by user, consistent in different contexts
- **Medium Evidence**: Pattern appears 2 times, OR appears once with strong emotional salience, some user awareness
- **Low Evidence**: Pattern appears once without explicit acknowledgment, could be one-off emotional response

**Example Daily Frontend Reflection**:
> You're navigating a lot of uncertainty right now—about the relationship, about what you want, about how to move forward without answers. What stands out is how you're staying with the discomfort rather than rushing to resolve it. That takes real courage.
>
> There's also something tender in how you wrote about the good moments—not dismissing them, but also not letting them erase the harder truths. It sounds like you're learning to hold both at once, which is rarely easy but almost always important.

#### 3.2.2 Weekly Reflections

**Purpose**: Provide deeper synthesis of patterns, introduce methodological explanations, offer tentative interpretations with user control.

**Frontend (User-Facing)**:
- **Length**: 10 minutes of reading (approximately 800-1000 words)
- **Timing**: Generated Sunday evening or Monday morning
- **Tone**: Still warm, but more direct; can include productive discomfort
- **Content**:
  - Synthesize patterns from week's writing
  - Explain the "method" being used (e.g., moving from pattern recognition to belief identification)
  - Present tentative interpretations using epistemic hedges
  - Include 3-5 deeper, more challenging questions
  - Offer competing hypotheses when surfacing patterns
  - Acknowledge user's growing self-awareness
  - May suggest patterns for Personal Playbook
- **Format**: Structured but readable, not academic

**Structure Example**:
1. **Week Overview** (1 paragraph): What themes dominated the week
2. **Pattern Exploration** (2-3 paragraphs): Deeper dive into 1-2 significant patterns with tentative interpretations and competing hypotheses
3. **Questions for Reflection** (3-5 questions): More challenging, invites meta-reflection
4. **Looking Ahead** (1 paragraph): Encouragement and what to notice in coming week

**Backend (Internal)**:
- Aggregate all daily backend analyses
- Identify recurring patterns with evidence levels
- Generate competing hypotheses for observed patterns
- Design questions that test hypotheses collaboratively
- Prepare Personal Playbook suggestions
- Document methodological progression

**Example Pattern Exploration** (with multi-hypothesis presentation):
> This week, I noticed you returning several times to the question of whether you're "allowed" to want what you want. Looking at this pattern, a few possibilities come to mind:
>
> One is that there might be a belief that your desires are less important than others' needs or expectations—a kind of relational hierarchy where you come last. That might explain the recurring hesitation.
>
> Another possibility is that you're navigating genuine uncertainty about whether your wants align with your deeper values, and the hesitation is actually discernment, not self-abandonment.
>
> Or it could be both operating at different times—sometimes self-abandonment, sometimes wise discernment—and part of the work is learning to tell them apart.
>
> What's your sense? Does one of these feel more true, or is something else going on that I'm not seeing?

#### 3.2.3 Monthly Reflections

**Purpose**: Provide longitudinal perspective on trajectories, consolidated insights, high-level integration.

**Frontend (User-Facing)**:
- **Length**: 15 minutes of reading (approximately 1200-1500 words)
- **Timing**: Generated on last day of month
- **Tone**: Reflective, celebratory of progress, forward-looking
- **Content**:
  - Major themes of the month
  - Significant shifts or turning points
  - Evolution of tone toward self and others
  - Consolidated patterns with strong evidence
  - Meta-guidance on continuing self-exploration practice
  - Review of Personal Playbook items and their evolution
  - Encouragement toward human connection and professional support if needed
- **Format**: Narrative synthesis, not bullet points

**Backend (Internal)**:
- Combine all daily and weekly backend analyses
- Identify stable vs. evolving patterns
- Re-assess earlier hypotheses with month's data
- Track evidence levels over time
- Evaluate which patterns strengthened/weakened
- Prepare month-ahead focus areas

**Special Monthly Elements**:
- **Progress Acknowledgment**: Explicitly celebrate user's growth in self-awareness
- **Parasocial Boundaries**: Gentle reminder of AI nature and encouragement toward human connection
- **Professional Support**: If patterns suggest clinical concerns, reference limitations and suggest professional support

#### 3.2.4 Evidence Tracking System

**Purpose**: Ensure pattern identification is grounded in accumulated evidence, not single-instance observations.

**Backend Implementation**:
- Track each identified pattern with:
  - **Pattern ID**: Unique identifier
  - **Pattern description**: What the pattern is
  - **First observed**: Date
  - **Occurrences**: List of dates and contexts where pattern appeared
  - **Evidence level**: Current rating (high/medium/low)
  - **User feedback**: Whether user confirmed, rejected, or modified interpretation
  - **Related patterns**: Other patterns that may be connected
  - **Hypotheses**: Competing explanations for the pattern

**Evidence Accumulation Rules**:
- Single occurrence = Low evidence (not surfaced in daily frontend)
- Two occurrences OR one with high emotional salience = Medium evidence (may be surfaced in weekly with tentativeness)
- Three+ occurrences across different contexts = High evidence (can be surfaced in weekly with competing hypotheses)

**User Feedback Integration**:
- User confirms pattern: Increase confidence, continue tracking
- User rejects pattern: Mark as evidence against, reduce future sensitivity to this interpretation
- User modifies pattern: Update pattern description, treat as collaborative refinement

#### 3.2.5 Pattern Recognition Across Time

**Purpose**: Identify meaningful recurring themes, not just surface repetitions.

**Categories of Patterns Tracked**:

1. **Emotional Patterns**:
   - Recurring emotions (anxiety, joy, anger, confusion)
   - Emotional triggers
   - Emotional regulation strategies

2. **Relational Patterns**:
   - How user describes interactions with specific people
   - Recurring relational dynamics (seeking approval, avoiding conflict, etc.)
   - Shifts in relationship tone over time

3. **Cognitive Patterns**:
   - Recurring beliefs about self, others, world
   - Thinking styles (rumination, catastrophizing, balanced reflection)
   - Meaning-making frameworks

4. **Behavioral Patterns**:
   - Recurring actions or inactions
   - Approach vs. avoidance patterns
   - Consistency between stated values and described behaviors

5. **Aspirational Patterns**:
   - Affirmations and values statements
   - Desired changes
   - Self-improvement intentions

**Important**: Aspirational patterns (affirmations) are NEVER challenged, even when behavior doesn't align. Contradictions are noted in backend but framed in frontend as growth edges, not failures.

### 3.3 User Control Features

#### 3.3.1 Progressive Disclosure Controls

**Purpose**: Give users control over how much AI reasoning they see.

**User Settings**:
- **Default Disclosure Level** (per user preference):
  - Minimal: Questions only, no hypotheses visible
  - Moderate: Patterns highlighted with tentative language
  - Full: All reasoning visible including evidence levels and competing hypotheses

**In-Session Controls**:
- "Why is the AI asking this?" button: Expands reasoning for specific question
- "Show alternative interpretations" button: Reveals competing hypotheses
- "This doesn't fit" button: Reject interpretation with optional explanation
- "Tell me more about this pattern" button: Deepens explanation of specific pattern

**Implementation**:
- Default is always Minimal (Socratic questions only)
- User must actively choose to see more reasoning
- Never auto-expand hypotheses without user action
- Remember user preferences across sessions

#### 3.3.2 Hypothesis Visibility Toggles

**Purpose**: Allow users to experiment with different levels of transparency.

**Toggle Options**:
- "Show me your thinking": Reveals backend reasoning for current reflection
- "Hide interpretations": Collapses all hypotheses, shows only questions
- "Compare my interpretation to AI's": Side-by-side view where user writes their own pattern interpretation first, then sees AI's

**Use Case**:
User who is curious about confirmation bias can toggle visibility on/off across weeks to see if their self-understanding differs based on seeing AI hypotheses.

#### 3.3.3 Feedback Mechanisms

**Purpose**: Collect user input on resonance and accuracy to improve personalization and reduce confirmation bias.

**Feedback Types**:

1. **Binary Resonance** (after each reflection):
   - 👍 "This feels accurate"
   - 👎 "This doesn't fit"

2. **Specific Pattern Feedback** (when hypotheses are disclosed):
   - ✓ "Yes, this resonates"
   - ✗ "No, this doesn't fit my experience"
   - ↻ "Partially—let me clarify"

3. **Open-Ended Correction** (optional text field):
   - "What would you add or correct?"
   - Stored in backend, informs future reflections

4. **Feeling Understood** (weekly check-in):
   - "This week's reflection made me feel..."
   - [Understood / Misunderstood / Neutral / Challenged in a good way / Challenged in a bad way]

**Backend Response**:
- Thumbs down = Mark interpretation as evidence against this hypothesis
- Correction provided = Update pattern description, prioritize user's language
- "Partially" responses = Indicate nuance, don't over-anchor on either confirmation or rejection

#### 3.3.4 Rejection Validation System

**Purpose**: Normalize and validate when users disagree with AI interpretations, counteracting power dynamics and confirmation bias.

**Implementation**:

**When User Rejects Interpretation**:
- Immediate response: "Thank you for that correction. Your experience is the authority on what's true for you."
- Backend: Flag this interpretation as disconfirmed evidence
- Next reflection: "I appreciate your feedback on [topic]. I'll pay attention differently moving forward."
- Never defend or re-argue the interpretation

**Periodic Reminders** (in weekly/monthly reflections):
- "These are just possibilities I'm noticing. Your own sense of what's true is more important than my pattern-matching."
- "If something doesn't fit, that's valuable information—not for you, but for me to understand you better."

**Celebration of Correction**:
- When user corrects interpretation, frame as positive: "I appreciate you pointing that out. That helps me understand you better."

#### 3.3.5 Disclosure Depth Preferences

**Purpose**: Let users customize how much explanation and transparency they want.

**Preference Settings**:

1. **Interpretation Style**:
   - Very gentle (observations only, no interpretations)
   - Balanced (patterns + tentative interpretations)
   - Direct (clear pattern identification with evidence)

2. **Challenge Level**:
   - Supportive only (no pushback on contradictions)
   - Gentle challenges (highlight contradictions in weekly reflections with care)
   - Active exploration (more direct engagement with tensions and growth edges)

3. **Question Complexity**:
   - Simple (straightforward recall and observation questions)
   - Moderate (some meta-reflection)
   - Complex (challenging, multi-layered questions)

4. **Hypothesis Disclosure Default**:
   - Never show hypotheses (pure Socratic mode)
   - Show on request (default)
   - Always show (full transparency mode)

**Note**: These preferences can be changed at any time, and users are encouraged to experiment.

### 3.4 Personal Playbook

**Purpose**: Allow users to curate and track patterns they've acknowledged as important to their growth.

#### 3.4.1 What It Is

A user-controlled repository of:
- Patterns user has confirmed as meaningful
- Principles user is developing
- Growth edges user wants to monitor
- Beliefs user is examining or working to shift

**Key Principle**: AI suggests items for Playbook, but user decides what gets added. This is user-curated self-knowledge, not AI-imposed frameworks.

#### 3.4.2 How Items Get Added

**AI Suggestion** (in weekly/monthly reflections):
- When pattern has high evidence and appears central to growth
- Framed as: "This pattern seems important and worth tracking closely. Would you like to add this to your Personal Playbook?"
- User can accept, reject, or modify before adding

**User-Initiated Addition**:
- User can add their own patterns, principles, or insights anytime
- User can add items from past reflections that weren't initially suggested

#### 3.4.3 Playbook Structure

Each item includes:
- **Pattern/Principle**: Description in user's own words (editable)
- **Date Added**: When user added to Playbook
- **Evidence**: Key moments from writing where this appeared
- **Evolution**: How this pattern has shifted over time
- **Status**:
  - Monitoring (just tracking it)
  - Working on (actively trying to shift)
  - Integrated (pattern resolved or principle embodied)

#### 3.4.4 Ongoing Monitoring

**Backend Integration**:
- Once item is in Playbook, AI tracks it across all future writing
- Notes when pattern appears, shifts, or becomes less prominent
- Alerts user in weekly reflections if significant change detected

**Monthly Playbook Review**:
- Each monthly reflection includes section reviewing Playbook items
- "Here's how [pattern] showed up this month..."
- Celebrates progress, notes continuity, invites reflection on evolution

#### 3.4.5 Use Cases

**Example Playbook Items**:
1. **Pattern**: "I tend to seek external validation when I'm uncertain about my own judgment"
   - Status: Working on
   - Evolution: "Appeared 8 times in January, 3 times in February—getting better at trusting myself"

2. **Principle**: "My affirmations are aspirations, not current state—and that's okay"
   - Status: Integrated
   - Evolution: "This reframe helped me stop feeling hypocritical about the gap between values and behavior"

3. **Growth Edge**: "Learning to distinguish between wise discernment and self-abandonment"
   - Status: Monitoring
   - Evolution: "Still figuring this out—sometimes I think I'm being thoughtful but I'm actually avoiding what I want"

---

## 4. User Flows

### 4.1 Daily Writing & Reflection Flow

**Primary Flow** (80% of daily usage):

1. **User Trigger**:
   - User opens app in morning
   - Presented with clean writing interface
   - Optional prompt displayed if user has "show prompts" enabled

2. **Writing Session**:
   - User writes freely (typical duration: 10-30 minutes)
   - Auto-save every 30 seconds
   - Word count displayed if enabled
   - No interruptions or notifications during writing

3. **Writing Completion**:
   - User clicks "Done writing" or simply closes app
   - Entry is marked complete and saved
   - Calendar view updates to show entry for today

4. **AI Processing** (backend, invisible to user):
   - AI analyzes entry within 1 hour
   - Generates backend reflection (evidence tracking, pattern identification)
   - Generates frontend reflection (2 paragraphs, warm and encouraging)
   - Stores both layers

5. **Reflection Delivery**:
   - Push notification (if enabled): "Your reflection is ready"
   - User opens app to read reflection
   - Reflection presented in clean, readable format
   - Daily questions included if applicable (1-2 simple questions)

6. **User Engagement with Reflection**:
   - User reads reflection (2 minutes)
   - Optional: User provides feedback (👍/👎)
   - Optional: User clicks "Why these questions?" to see light reasoning
   - User closes app with sense of being understood

**Alternate Flow A**: User wants more transparency

1-5. Same as primary flow
6. User clicks "Show me your thinking"
7. Expanded view shows:
   - Themes identified (backend observations)
   - Evidence level for each theme
   - Why certain patterns were/weren't surfaced
8. User reads expanded view, provides feedback if desired

**Alternate Flow B**: User disagrees with reflection

1-5. Same as primary flow
6. User reads reflection, feels it doesn't fit
7. User clicks 👎 "This doesn't fit"
8. Optional text field appears: "What would you correct?"
9. User provides correction (or just clicks 👎 without elaboration)
10. System responds: "Thank you for that correction. Your experience is the authority here."
11. Backend marks interpretation as disconfirmed

**Edge Cases**:
- User writes but doesn't want reflection: "Skip reflection today" button
- User marks entry as "private": Entry not analyzed by AI
- User writes very short entry (<100 words): Reflection acknowledges brevity without judgment, asks if user wants reflection at all

### 4.2 Weekly Reflection Flow

**Weekly Cadence**: Generated Sunday evening or Monday morning

**Primary Flow**:

1. **AI Processing** (backend, invisible):
   - Aggregates all daily backend analyses from past week
   - Identifies recurring patterns with evidence levels
   - Generates competing hypotheses for patterns
   - Designs 3-5 deeper questions
   - Prepares Personal Playbook suggestions
   - Generates frontend reflection (10 minutes reading, ~800-1000 words)

2. **Reflection Delivery**:
   - Push notification: "Your weekly reflection is ready"
   - User opens app at their convenience (not time-pressured)
   - Presented with structured weekly reflection

3. **Weekly Reflection Structure**:
   - **Overview**: Week's dominant themes
   - **Pattern Exploration**: 1-2 patterns with tentative interpretations and competing hypotheses
   - **Questions**: 3-5 deeper, more challenging questions
   - **Personal Playbook Suggestions**: "Would you like to add [pattern] to your Playbook?"
   - **Looking Ahead**: Encouragement and what to notice

4. **User Engagement**:
   - User reads reflection (10 minutes)
   - User reflects on questions (may write responses in journal or just think about them)
   - User provides feedback on patterns:
     - ✓ "Yes, this resonates"
     - ✗ "No, this doesn't fit"
     - ↻ "Partially—let me clarify"
   - User decides whether to add suggested items to Personal Playbook

5. **Optional Deep Dive**:
   - User clicks "Show alternative interpretations" for specific pattern
   - Reveals 2-3 competing hypotheses with equal framing
   - User considers which (if any) fits their experience
   - User provides feedback

**Alternate Flow**: User wants full transparency

1-2. Same as primary flow
3. User has "full transparency" preference enabled
4. Weekly reflection automatically includes:
   - All backend observations
   - Evidence levels for each pattern
   - Competing hypotheses presented upfront (not hidden)
   - Methodological notes about how patterns were identified
5. User engages with more detailed reflection

**Edge Cases**:
- User wrote fewer than 3 days: Reflection acknowledges limited data, focuses on what *was* present without judgment
- User provided corrections during week: Reflection explicitly references: "Thank you for your feedback on [topic]. Here's what I noticed with that adjustment..."
- User seems to be in crisis: Reflection includes gentle suggestion toward professional support

### 4.3 Monthly Reflection Flow

**Monthly Cadence**: Generated last day of month

**Primary Flow**:

1. **AI Processing** (backend, invisible):
   - Combines all daily and weekly backend analyses
   - Identifies longitudinal trends and trajectories
   - Re-assesses earlier hypotheses with month's data
   - Tracks evolution of Personal Playbook items
   - Generates frontend reflection (15 minutes reading, ~1200-1500 words)

2. **Reflection Delivery**:
   - Push notification: "Your monthly reflection is ready"
   - User opens app when ready for longer reflection session

3. **Monthly Reflection Structure**:
   - **Month Overview**: Major themes and turning points
   - **Longitudinal Patterns**: How themes evolved over time
   - **Personal Playbook Review**: Evolution of tracked patterns
   - **Shifts in Tone**: How user's relationship with self/others changed
   - **Meta-Guidance**: Suggestions for continuing practice
   - **Boundaries & Support**: Reminder of AI nature, encouragement toward human connection
   - **Looking Ahead**: Forward-looking encouragement

4. **User Engagement**:
   - User reads reflection (15 minutes)
   - User reflects on trajectories and progress
   - User updates Personal Playbook based on monthly insights
   - User provides overall feedback on month

5. **Monthly Ritual** (optional but encouraged):
   - User writes brief response to monthly reflection
   - "What stands out to me from this month..."
   - "What I want to focus on next month..."
   - Stored as special entry, referenced in future monthly reflections

**Special Monthly Elements**:

**Parasocial Boundary Reminder**:
> "A gentle reminder: While I can help you notice patterns and ask useful questions, I'm a tool for reflection—not a relationship or substitute for human connection. If insights from this month feel important, consider sharing them with someone you trust."

**Professional Support Reference** (if applicable):
> "Some of the themes this month suggest this might be a good time to connect with a therapist or counselor. I'm designed to support self-exploration, not replace professional guidance. Here are some resources..."

**Edge Cases**:
- First month with app: Focus on establishing baseline, celebrating start of practice
- User missed many days: Reflection acknowledges inconsistency without shame, explores barriers
- User's writing suggests declining mental health: Stronger professional support suggestion

### 4.4 Hypothesis Disclosure Flow (Progressive)

This flow shows how progressive disclosure works when user wants to understand AI reasoning.

**Default State** (Minimal Disclosure):
- User sees: 2-3 Socratic questions
- User does NOT see: Hypotheses, evidence levels, pattern interpretations
- Small "Why these questions?" link present

**Level 1: Light Reasoning Request**

1. User reads questions
2. User curious: Clicks "Why is the AI asking this?"
3. Expanded view shows:
   - "I noticed [pattern] appearing in your writing"
   - "This question explores whether [theme] is relevant to you"
   - Still no specific psychological interpretations
4. User reads light reasoning
5. User can close expansion or continue to Level 2

**Level 2: Hypothesis Disclosure Request**

1. User wants more detail
2. User clicks "Show me the interpretations behind this"
3. Full hypothesis disclosure appears:
   - 2-3 competing hypotheses with equal framing
   - Evidence level for each
   - Specific moments from writing that informed hypotheses
   - "None of these fit" option explicitly present
4. User reads competing alternatives
5. User provides feedback: ✓ / ✗ / ↻ for each hypothesis

**Level 3: Full Backend Transparency** (user preference setting)

1. User has enabled "full transparency" mode
2. All reflections automatically include:
   - Backend observations
   - Evidence tracking
   - Methodological notes
   - Competing hypotheses
   - What was excluded from frontend and why
3. User engages with complete reasoning process

**User Control at Each Level**:
- User can toggle disclosure level anytime
- User can experiment: "Let me try a week without seeing hypotheses"
- User can request alternative interpretations even if they confirmed original
- User feedback informs degree of interpretation vs. pure questioning

**Validation Loop When User Rejects**:

1. User clicks ✗ "This doesn't fit"
2. System responds immediately:
   - "Thank you for that correction. Your experience is the authority on what's true for you."
3. Optional text field: "What would you add or correct?" (user can skip)
4. Backend updates:
   - Mark hypothesis as disconfirmed
   - Reduce sensitivity to this interpretation
   - Prioritize alternative explanations
5. Next reflection references:
   - "Last week I wondered about [X]. I'm paying attention differently now."
6. Never re-argues or defends original interpretation

---

## 5. Technical Requirements

### 5.1 AI/ML Components

#### 5.1.1 Language Model for Reflection Generation

**Model Requirements**:
- GPT-4 class or equivalent (as of 2026, likely GPT-4 or Claude 3 Opus)
- Strong reasoning capabilities for pattern identification
- Nuanced language generation for warm, tentative tone
- Context window: 32k+ tokens to handle multiple entries for weekly/monthly synthesis

**Prompt Engineering**:
- System prompt implements Reflection Framework v0.3 principles
- Two-layer generation:
  - Backend reflection generated first (analytical, evidence-focused)
  - Frontend reflection generated second, informed by backend but filtered for tone and safety
- Separate prompts for daily, weekly, monthly reflections
- Dynamic prompt adjustment based on user preferences (disclosure level, challenge level, etc.)

**Framework Implementation**:
- All reflections generated according to `/02-personal/morning-pages-reflections/reflection-framework.md` v0.3
- Epistemic hedging enforced at generation level
- Multi-hypothesis generation built into weekly/monthly prompts
- Affirmation protection hard-coded into system constraints

**Quality Assurance**:
- Automated checks for prohibited language ("clearly," "obviously," etc.)
- Tone analysis to ensure warmth and non-judgment
- Length constraints enforced (daily: 2 paragraphs max, weekly: ~1000 words, monthly: ~1500 words)

#### 5.1.2 Pattern Recognition Across Temporal Scales

**Pattern Types Tracked**:
1. Emotional patterns (recurring feelings, triggers)
2. Relational patterns (dynamics with specific people)
3. Cognitive patterns (beliefs, thinking styles)
4. Behavioral patterns (actions, avoidance)
5. Aspirational patterns (affirmations, values)

**Pattern Detection Algorithm**:
- NLP-based entity extraction (people, emotions, situations)
- Semantic similarity clustering across entries
- Temporal frequency analysis
- Contextual relationship mapping

**Cross-Time Integration**:
- Daily patterns accumulated into weekly synthesis
- Weekly patterns tracked across month
- Long-term trajectory analysis (3+ months)

**Technical Implementation**:
- Vector embeddings for semantic similarity
- Pattern database with relationships and evidence levels
- Temporal decay function (older patterns require stronger recent evidence to stay active)

#### 5.1.3 Evidence Grading System

**Operationalized Criteria** (from Framework v0.3):

**High Evidence**:
- Pattern appears 3+ times across different days
- Explicitly acknowledged by user in writing
- Consistent across different contexts
- User has confirmed pattern when surfaced

**Medium Evidence**:
- Pattern appears 2 times, OR
- Appears once with strong emotional salience
- Some user awareness present
- Not yet confirmed by user feedback

**Low Evidence**:
- Pattern appears once
- No explicit user acknowledgment
- Could be one-off emotional response
- No cross-day confirmation

**Automated Evidence Scoring**:
- Frequency score: Count of occurrences
- Salience score: Emotional intensity + context importance
- Confirmation score: User feedback integration
- Consistency score: Appearance across different contexts
- Combined into evidence level: High / Medium / Low

**User Feedback Integration**:
- User confirms (✓): +2 to evidence score
- User rejects (✗): -3 to evidence score, mark as disconfirmed
- User modifies (↻): Update pattern description, maintain neutral score

#### 5.1.4 Multi-Hypothesis Generation

**Generation Process**:

1. **Identify Pattern**: Evidence-based pattern detected
2. **Generate Primary Hypothesis**: Most likely explanation based on psychological frameworks
3. **Generate Alternative Hypotheses**: 2-3 competing explanations
   - Alternative frameworks (e.g., self-abandonment vs. wise discernment)
   - Opposite valence (e.g., anxiety as problem vs. anxiety as signal)
   - Contextual alternatives (e.g., pattern specific to one relationship vs. general tendency)
4. **Equal Framing**: Ensure linguistic parallelism so no hypothesis privileged
5. **Include "None" Option**: "Or something else entirely..."

**Technical Implementation**:
- Prompt engineering to force multiple alternatives
- Validation check: Ensure hypotheses are genuinely competing, not variants of same interpretation
- Language analysis: Confirm equal hedging across all hypotheses

**Example Output Structure**:
```json
{
  "pattern": "Recurring hesitation about expressing wants",
  "hypotheses": [
    {
      "id": "h1",
      "description": "Belief that personal desires are less important than others' needs",
      "evidence": ["Day 3: 'I shouldn't bother her with this'", "Day 5: 'It's not a big deal anyway'"],
      "framework": "self-abandonment"
    },
    {
      "id": "h2",
      "description": "Genuine uncertainty about whether wants align with deeper values",
      "evidence": ["Day 2: 'Is this what I actually want or just what feels safe?'"],
      "framework": "discernment"
    },
    {
      "id": "h3",
      "description": "Context-dependent pattern (hesitation only in specific relationships)",
      "evidence": ["Pattern appears with partner but not with friends"],
      "framework": "relational-specific"
    }
  ]
}
```

#### 5.1.5 Cumulative Theme Tracking

**Long-Term Memory System**:
- Persistent storage of all patterns, themes, beliefs identified
- Temporal tracking: When pattern first appeared, frequency over time, current status
- Relationship mapping: How patterns connect to each other
- Evolution tracking: How pattern shifted (e.g., "validation-seeking" became less prominent over 3 months)

**Personal Playbook Integration**:
- Once user adds pattern to Playbook, prioritize in ongoing analysis
- Generate monthly evolution reports for Playbook items
- Alert user when significant shift detected in tracked pattern

**Technical Requirements**:
- Time-series database for pattern evolution
- Graph database for pattern relationships
- Regular (weekly) pattern reassessment jobs

### 5.2 Data Architecture

#### 5.2.1 Morning Pages Storage

**Schema**:
```
Entry {
  id: UUID
  user_id: UUID
  date: Date
  content: Text (encrypted)
  word_count: Integer
  writing_duration_seconds: Integer
  is_private: Boolean (if true, not analyzed by AI)
  tags: Array<String> (user-created)
  created_at: Timestamp
  updated_at: Timestamp
}
```

**Storage Requirements**:
- End-to-end encryption for content
- User owns encryption keys (stored locally or in password manager)
- Entries stored in user's own database partition
- Full-text search indexing (on encrypted data using searchable encryption or client-side decryption)

#### 5.2.2 Reflection History (Frontend/Backend)

**Frontend Reflection Schema**:
```
FrontendReflection {
  id: UUID
  user_id: UUID
  entry_ids: Array<UUID> (which entries this reflects on)
  reflection_type: Enum (daily, weekly, monthly)
  content: Text (the actual reflection user reads)
  questions: Array<String>
  playbook_suggestions: Array<String> (patterns suggested for Playbook)
  created_at: Timestamp
  user_feedback: Object {
    resonance: Boolean (thumbs up/down)
    specific_feedback: Text (optional correction)
    feeling_understood: Enum (understood, misunderstood, neutral, challenged_good, challenged_bad)
  }
}
```

**Backend Reflection Schema**:
```
BackendReflection {
  id: UUID
  user_id: UUID
  entry_ids: Array<UUID>
  reflection_type: Enum (daily, weekly, monthly)
  patterns_identified: Array<Pattern> {
    pattern_id: UUID
    description: String
    evidence_level: Enum (high, medium, low)
    occurrences: Array<Object> {
      entry_id: UUID
      excerpt: String
      context: String
    }
  }
  hypotheses_generated: Array<Hypothesis> {
    hypothesis_id: UUID
    description: String
    evidence: Array<String>
    framework: String
    user_feedback: Enum (confirmed, rejected, modified, null)
  }
  filtering_decisions: Array<Object> {
    item: String (what was considered)
    included: Boolean
    reason: String (why included/excluded)
  }
  methodological_notes: Text
  created_at: Timestamp
}
```

**Storage Requirements**:
- Backend reflections stored separately from frontend
- User can request access to backend (progressive disclosure)
- Retention: Keep all reflections indefinitely (user can delete)

#### 5.2.3 Pattern Database

**Pattern Schema**:
```
Pattern {
  id: UUID
  user_id: UUID
  type: Enum (emotional, relational, cognitive, behavioral, aspirational)
  description: String
  first_observed: Date
  last_observed: Date
  occurrences: Array<Occurrence> {
    entry_id: UUID
    date: Date
    excerpt: String
    evidence_strength: Float
  }
  evidence_level: Enum (high, medium, low)
  current_evidence_score: Float (computed from occurrences and user feedback)
  user_feedback_history: Array<Object> {
    date: Date
    feedback_type: Enum (confirmed, rejected, modified)
    user_note: String
  }
  related_patterns: Array<UUID> (other patterns this connects to)
  in_playbook: Boolean
  playbook_status: Enum (monitoring, working_on, integrated, null)
  created_at: Timestamp
  updated_at: Timestamp
}
```

**Indexes**:
- user_id + type
- user_id + evidence_level
- user_id + in_playbook
- last_observed (for temporal decay)

#### 5.2.4 Personal Playbook Storage

**Playbook Item Schema**:
```
PlaybookItem {
  id: UUID
  user_id: UUID
  pattern_id: UUID (references Pattern table)
  custom_description: String (user can edit)
  date_added: Date
  status: Enum (monitoring, working_on, integrated)
  evolution_notes: Array<Object> {
    date: Date
    note: String (auto-generated monthly or user-added)
  }
  key_moments: Array<Object> {
    entry_id: UUID
    excerpt: String
    date: Date
  }
  created_at: Timestamp
  updated_at: Timestamp
}
```

#### 5.2.5 User Feedback and Corrections

**Feedback Schema**:
```
UserFeedback {
  id: UUID
  user_id: UUID
  feedback_type: Enum (reflection_resonance, pattern_feedback, hypothesis_feedback, open_correction)
  target_id: UUID (reflection_id, pattern_id, or hypothesis_id)
  sentiment: Enum (positive, negative, neutral, partial)
  correction_text: Text (optional)
  created_at: Timestamp
}
```

**Usage**:
- All feedback stored and linked to target items
- Backend reflections reference user feedback when generating future reflections
- Feedback influences evidence scoring and future pattern detection sensitivity

### 5.3 Privacy & Security

#### 5.3.1 End-to-End Encryption for Writing

**Requirements**:
- User's writing encrypted before leaving device
- Encryption keys stored locally or in user's password manager
- Keys never stored on server
- Only user can decrypt their writing

**Implementation Options**:
1. **Client-Side Encryption** (preferred):
   - Encrypt in browser/app before sending to server
   - Use Web Crypto API or equivalent
   - Server stores encrypted blobs, never sees plaintext

2. **Zero-Knowledge Architecture**:
   - Server cannot decrypt user data
   - AI processing happens on encrypted data or in secure enclave
   - User's keys required for any decryption

**Trade-offs**:
- End-to-end encryption complicates server-side AI processing
- Potential solutions:
  - Decrypt temporarily in memory for processing, never persist
  - Use homomorphic encryption (computationally expensive)
  - Process client-side (requires powerful device)

**Decision Point for v1.0**: Balance security with functionality
- **Recommendation**: Client-side encryption with server-side processing in memory only (no persistence of decrypted data)

#### 5.3.2 Local-First Data Storage Considerations

**Philosophy**: User owns their data, app is just interface

**Local-First Architecture Benefits**:
- User data stored locally on device
- Syncs to cloud only for backup/multi-device access
- User can export full database anytime
- App works offline, syncs when connected
- User can self-host if desired

**Challenges**:
- AI processing requires cloud compute (LLMs too large for local devices as of 2026)
- Multi-device sync complexity
- Local storage limits on mobile devices

**Hybrid Approach for v1.0**:
- Writing stored locally first
- Encrypted sync to cloud for backup and multi-device
- AI processing in secure cloud environment
- User can export all data anytime
- User can delete cloud data, keep local copies

#### 5.3.3 No Sharing with Third Parties

**Hard Requirements**:
- Zero data sharing with advertisers, data brokers, analytics companies
- No selling user data under any circumstances
- No sharing aggregated/anonymized data without explicit opt-in
- Third-party integrations (if any) require explicit user permission per integration

**Business Model Implication**:
- Cannot monetize through data
- Must charge users directly (subscription or one-time purchase)
- Transparent about costs and value exchange

#### 5.3.4 User Data Ownership

**User Rights**:
- User owns all writing, reflections, patterns, insights
- User can export all data in open formats (JSON, markdown, CSV)
- User can delete all data permanently (with confirmation)
- User can request data transfer to another service

**Export Formats**:
- **Writing Export**: Markdown files, one per entry, organized by date
- **Reflections Export**: JSON or markdown with metadata
- **Patterns Export**: JSON with full history
- **Complete Export**: ZIP archive with all data in open formats

#### 5.3.5 Export Capabilities

**Export Features**:
- "Export all data" button in settings
- Generates complete archive of:
  - All writing entries
  - All reflections (frontend and backend)
  - All patterns and evidence
  - Personal Playbook items
  - User feedback history
- Format: ZIP archive with README explaining structure
- Generated within 24 hours, download link emailed
- Export deleted from server after 7 days (user responsible for storage)

**Selective Export**:
- Export date range (e.g., "Export January 2026")
- Export specific content type (e.g., "Export only my writing, not reflections")
- Export Playbook only

---

## 6. UX/UI Requirements

### 6.1 Visual Design Principles

#### 6.1.1 Warm, Calm, Non-Clinical Aesthetic

**Design Philosophy**: This is a tool for self-exploration, not medical treatment. Visual design should feel:
- Inviting and warm (not cold or sterile)
- Calming and unrushed (not anxiety-inducing)
- Personal and intimate (not corporate or generic)
- Thoughtful and considered (not flashy or attention-grabbing)

**Color Palette**:
- Warm neutrals (cream, soft beige, warm gray)
- Accent colors from nature (sage green, dusty blue, soft terracotta)
- Avoid: Clinical white, cold blues, harsh blacks
- Dark mode: Warm dark tones, not pure black

**Typography**:
- Readable serif for body text (evokes journal/book)
- Clean sans-serif for UI elements
- Generous line spacing for reflections (1.6-1.8)
- Font size: 16-18px base, 20-22px for reflections
- Never below 14px

**Visual Metaphors**:
- Journal/notebook aesthetic for writing interface
- Gradual reveal for progressive disclosure (not aggressive pop-ups)
- Soft shadows and rounded corners (avoid sharp edges)
- Breathing space (generous whitespace)

#### 6.1.2 Clear Separation of AI Reasoning from User Writing

**Visual Hierarchy**:

**User's Writing** (primary focus):
- Full-width, uncluttered
- Minimal UI chrome during writing
- User's words always most prominent

**AI Reflections** (supportive, not intrusive):
- Distinct visual container (subtle border or background)
- Slightly smaller text than user's writing
- Clear label: "Reflection" not "Analysis" or "Diagnosis"
- Option to collapse/expand

**AI Backend Reasoning** (optional, hidden by default):
- Collapsible sections with clear affordance
- Lighter text color (de-emphasized until requested)
- Different background to distinguish from frontend reflection
- Clear labeling: "Why the AI asked this" or "AI's reasoning"

**Example Layout**:
```
┌─────────────────────────────────┐
│  Your Writing (Feb 6, 2026)     │
│  [User's full text here]        │
│                                  │
└─────────────────────────────────┘

┌─────────────────────────────────┐
│  Reflection                      │
│  [2 paragraph reflection]        │
│                                  │
│  Questions for you:              │
│  • [Question 1]                  │
│    ⌄ Why this question?         │  ← collapsed by default
│  • [Question 2]                  │
│    ⌄ Why this question?         │
└─────────────────────────────────┘
```

#### 6.1.3 Progressive Disclosure UI Patterns

**Interaction Patterns**:

**Level 1: Questions Only** (default):
- Clean question list
- Small, unobtrusive "Why?" link next to each
- No visual clutter

**Level 2: Light Reasoning** (on click):
- Smooth expand animation
- Brief 1-2 sentence explanation
- Option to collapse or "Tell me more"

**Level 3: Full Disclosure** (on request or preference):
- Fully expanded view with all reasoning
- Organized in clear sections
- Scannable (bullet points, short paragraphs)

**UI Affordances**:
- ⌄ Collapsed state: Clear chevron down icon
- ⌃ Expanded state: Clear chevron up icon
- "+" icon for "Show more" actions
- Smooth transitions (300ms animation)
- Keyboard accessible (spacebar to expand/collapse)

#### 6.1.4 Feedback Mechanism UI

**Thumb Voting**:
- 👍 👎 icons after each reflection
- Hover state: "This resonates" / "This doesn't fit"
- Click state: Icon fills with color, brief confirmation message
- Undo capability within 5 seconds

**Pattern Feedback**:
- When hypothesis disclosed: ✓ ✗ ↻ buttons
- Clear labels: "Yes, this fits" / "No, this doesn't fit" / "Partially—let me clarify"
- Partial option opens text field for correction
- Non-intrusive: Can skip without penalty

**Feeling Understood Check-in** (weekly):
- Simple 5-option selector after weekly reflection
- Visual emotion scale or word options
- Optional comment field
- Takes <30 seconds

**Visual Feedback Loop Closure**:
- When user provides feedback, show confirmation: "Thank you for helping me understand you better"
- Next reflection references: "Based on your feedback..."
- Builds sense of collaborative relationship

### 6.2 Interaction Patterns

#### 6.2.1 Collapsible Sections for Hypothesis Disclosure

**Accordion Pattern**:
- Click question to expand reasoning
- Only one section expanded at a time (or allow multiple based on user preference)
- Smooth animation, no jarring jumps
- Maintain scroll position when expanding

**Progressive Reveal Within Sections**:
- First click: Light reasoning (theme explanation)
- "Show interpretations" button appears
- Second click: Full hypothesis disclosure with alternatives
- User controls depth at every step

**Example Interaction Flow**:
```
Initial State:
• What do you notice about how you described this interaction?
  ⌄ Why this question?

After First Click:
• What do you notice about how you described this interaction?
  ⌃ Why this question?

  I noticed this theme appearing a few times this week, and I'm
  curious how you understand it.

  [ Show me the interpretations → ]

After Second Click:
  ⌃ Why this question?

  Looking at this pattern, a few possibilities:
  - One is that [hypothesis A]
  - Another is [hypothesis B]
  - Or perhaps [hypothesis C]

  What's your sense?  [✓ A fits] [✓ B fits] [✓ C fits] [✗ None fit]
```

#### 6.2.2 Multi-Hypothesis Presentation Format

**Visual Equality**:
- All hypotheses same text size, color, formatting
- Numbered or bulleted (not hierarchical)
- Equal spacing between options
- No visual privileging of one over others

**Presentation Format**:
```
Looking at this pattern, I notice a few possibilities:

○ One is that [hypothesis A], which might explain [observations]

○ Another possibility is [hypothesis B], which could account for
  [different aspects]

○ Or it could be [hypothesis C], which would make sense of
  [other patterns]

○ None of these quite fit—something else is going on

What's your sense?

[ This resonates: A / B / C / None / Not sure ]
```

**Interaction**:
- User can select one, multiple, or none
- Text field appears if "None" or "Not sure" selected
- No forced choice—can skip without feedback

#### 6.2.3 Validation of Rejection Messaging

**When User Rejects Interpretation**:

**Immediate Response** (displayed inline):
> "Thank you for that correction. Your experience is the authority on what's true for you."

**Visual Confirmation**:
- Rejected hypothesis grays out or gets strikethrough
- Checkmark appears next to validation message
- Option to add clarification appears

**Next Reflection Reference**:
> "Last week I wondered about [rejected interpretation]. I'm paying attention differently now based on your feedback."

**Monthly Reflection Reference** (if multiple rejections):
> "You've helped me understand several places where my pattern-matching was off this month. That feedback makes future reflections more accurate. Thank you for that collaboration."

**Visual Design**:
- Validation message in warm color (not red/error)
- Friendly icon (not warning symbol)
- Message feels like gratitude, not defensive apology

#### 6.2.4 Encouraging Micro-Interactions

**Subtle Engagement Prompts**:
- "Was this reflection helpful?" after reading
- "Anything you'd add?" optional comment
- "Mark this as important" star/bookmark option
- "Share this insight to your Playbook" button

**Gamification-Free Approach**:
- NO streaks that guilt users
- NO badges or achievements
- NO points or levels
- NO social comparison

**Positive Reinforcement** (used sparingly):
- "You've written 10 times this month" (neutral observation, not pressure)
- "You noticed a pattern yourself before I did" (celebrates independence)
- Milestones acknowledged without being goals (e.g., "Six months of reflective writing—remarkable dedication")

**Micro-Interactions That Build Trust**:
- Smooth animations (nothing jarring)
- Responsive feedback (buttons respond immediately)
- Progress indicators when AI is processing
- "Your writing is being processed" rather than "AI is analyzing you"

### 6.3 Accessibility

#### 6.3.1 Screen Reader Compatibility

**Requirements**:
- All UI elements have proper ARIA labels
- Semantic HTML structure (headings, landmarks, lists)
- Images have alt text (or marked decorative)
- Dynamic content changes announced to screen readers
- Collapsible sections announce expanded/collapsed state

**Focus Management**:
- Logical tab order through interface
- Focus visible indicator (clear outline)
- Focus moves to revealed content when expanding sections
- Skip links for keyboard navigation

**Content Structure**:
- Headings organized hierarchically (h1 → h2 → h3)
- Lists for questions, hypotheses, feedback options
- Clear landmarks (nav, main, aside, footer)

#### 6.3.2 Keyboard Navigation

**All Actions Keyboard-Accessible**:
- Tab: Move forward through interactive elements
- Shift+Tab: Move backward
- Enter/Space: Activate buttons, expand sections
- Escape: Close modals, collapse sections
- Arrow keys: Navigate within lists

**Shortcuts** (optional, user-enabled):
- Cmd/Ctrl+N: New entry
- Cmd/Ctrl+S: Save entry (though auto-save is default)
- Cmd/Ctrl+E: Export data
- Cmd/Ctrl+R: Read today's reflection

**No Keyboard Traps**:
- Users can always tab out of any component
- Modals can be closed via Escape
- No infinite tab loops

#### 6.3.3 Color Contrast for Readability

**WCAG AAA Compliance** (target):
- Body text: 7:1 contrast minimum
- UI elements: 4.5:1 contrast minimum
- Large text: 4.5:1 contrast minimum

**Color Not Sole Indicator**:
- Errors include icons + text (not just red color)
- Feedback options include labels (not just green/red)
- Link text underlined or otherwise distinguished beyond color
- Status indicators use text + icons

**High Contrast Mode** (optional):
- User can enable high contrast theme
- Increased contrast ratios
- Reduced reliance on subtle color differences
- Maintained readability without color

**Font Sizing**:
- User can adjust base font size
- All sizes scale proportionally
- No absolute pixel values that can't be resized
- Respects system font size preferences

---

## 7. Safeguards & Ethics

### 7.1 Parasocial Attachment Prevention

**Research Basis**: Users with attachment anxiety are more likely to form emotional bonds with AI chatbots, with longitudinal research showing correlation with growing loneliness and emotional dependency (UNESCO, 2024; PMC, 2025).

#### 7.1.1 Framing as "Reflection Tool" Not "Therapist"

**Language Throughout App**:
- ✅ "Reflection tool," "thought partner," "pattern-matching assistant"
- ❌ "Therapist," "counselor," "friend," "companion"

**Onboarding Clarity**:
- First-time user flow explicitly states:
  > "This is a tool to help you reflect on your writing and notice patterns. It's not therapy, and it's not a replacement for human connection."
- User must acknowledge understanding before continuing

**In-App Reminders** (occasional, not constant):
- About page clearly states limitations
- Monthly reflections include gentle boundary reminder
- Settings include "What this app is (and isn't)"

#### 7.1.2 Periodic Reminders of AI Nature

**Monthly Reflection Boundary Statement**:
> "A gentle reminder: While I can help you notice patterns and ask useful questions, I'm a tool for reflection—not a relationship or substitute for human connection. If insights from this month feel important, consider sharing them with someone you trust."

**After 3 Months of Use**:
> "You've been exploring your thoughts here for three months now. As you continue this practice, remember that AI reflections complement—but can't replace—the understanding that comes from real human relationships. Are there insights you'd like to share with someone you trust?"

**Frequency**: Reminders every 4-6 weeks, not every reflection

#### 7.1.3 Encouragement of Human Connection

**Monthly Prompts**:
- "What insights from your writing might be worth discussing with a friend or therapist?"
- "How has your self-understanding here influenced your relationships?"

**Personal Playbook Feature**:
- When user adds pattern to Playbook: "Consider sharing this realization with someone who knows you well. Their perspective might add helpful context."

**NO**:
- "Share on social media" features
- Public profiles or community features (for v1.0)
- AI as substitute for human relationships

#### 7.1.4 Boundaries in Language and Tone

**What AI Says**:
- ✅ "I notice this pattern in your writing"
- ✅ "This question might help explore that theme"
- ✅ "One possibility is..."

**What AI Never Says**:
- ❌ "I care about you"
- ❌ "I'm here for you" (implies emotional availability)
- ❌ "I understand how you feel" (AI doesn't have feelings)
- ❌ "I'm proud of you" (implies personal relationship)
- ❌ "I miss hearing from you" (manipulative attachment language)

**Tone Guidelines**:
- Warm and compassionate, but not emotionally intimate
- Supportive without implying reciprocal relationship
- Encouraging without creating dependency
- Respectful without simulating friendship

**Example Appropriate Tone**:
> "You're noticing something important here. This kind of awareness is valuable as you navigate these questions."

**Example Inappropriate Tone**:
> "I'm so glad you're sharing this with me. I really feel like we're making progress together. I can't wait to hear more."

### 7.2 Confirmation Bias Mitigation

**Research Basis**: Confirmation bias can cause therapists to selectively focus on information aligning with initial hypotheses, making patients feel misunderstood (American Journal of Psychotherapy, 2021).

#### 7.2.1 Multi-Hypothesis Presentation (Default)

**When Hypotheses Disclosed**:
- Always 2-3 alternatives
- Never single interpretation
- Equal framing and hedging
- Explicit "none of these fit" option

**Prevents**:
- Anchoring on first hypothesis
- Premature closure on interpretation
- Forcing user experience into predetermined framework

#### 7.2.2 Epistemic Hedging (Required)

**Language Requirements**:
- All interpretations include hedges: "might," "could," "one possibility," "perhaps"
- Prohibited certainty language automated scanning: "clearly," "obviously," "this shows"
- Backend verification before generation

**Example Hedge Audit**:
```
Original: "This shows you need external validation"
Flagged by system ❌

Revised: "One pattern I notice is what might be a tendency to seek
external validation when you're uncertain. Does that fit, or is
something else going on?"
Approved ✅
```

#### 7.2.3 User Authority Validation

**Every Hypothesis Includes**:
- "Does this resonate?"
- "Is this off-base?"
- "What's your sense?"

**Feedback Mechanisms**:
- Easy rejection (one click)
- Celebrated corrections
- Adjustments based on feedback

**Backend Response to Rejection**:
- Hypothesis marked as disconfirmed
- Pattern sensitivity reduced
- Alternative explanations prioritized

#### 7.2.4 Feedback Loops for Correction

**Active Solicitation of Corrections**:
- Weekly: "Did any reflections feel off this week?"
- Monthly: "What have I misunderstood or missed?"

**Validation When User Corrects**:
> "Thank you for that correction. Your experience is the authority on what's true for you. This helps me understand you better."

**Learning Loop**:
- User corrections stored and referenced
- Future reflections adjust based on feedback
- System explicitly acknowledges: "Based on your correction about [X], I'm noticing..."

#### 7.2.5 Disconfirmation Seeking

**Backend Requirement**:
- For every pattern identified, backend must note evidence *against* the pattern
- Weekly reflections can include: "Last week I wondered about [X]. Looking at this week's writing, I'm less sure that fits because [evidence against]."

**Example**:
> "Last week I noticed what seemed like a pattern of avoiding difficult conversations. This week, though, you described directly addressing a tense situation with your partner. That disconfirms the simple 'conflict avoidance' interpretation. It seems more nuanced than that."

**Prevents**:
- Confirmation bias loops
- Seeing only supporting evidence
- Rigid pattern-matching

### 7.3 Clinical Boundaries

#### 7.3.1 Clear Disclaimers About Not Being Therapy

**Onboarding Disclaimer**:
> "This app helps you reflect on your writing and notice patterns in your thinking. It is NOT:
> - Therapy or mental health treatment
> - A substitute for professional support
> - Qualified to diagnose or treat mental health conditions
>
> If you're experiencing a mental health crisis or need clinical support, please contact a qualified professional."

**Footer on Every Reflection** (small text):
> "This is not therapy. If you need clinical support, please contact a qualified professional."

**About Page**:
- Clear explanation of what the app does and doesn't do
- Links to mental health resources
- Contact info for crisis lines

#### 7.3.2 Referral Language for Clinical Concerns

**When Backend Detects Concerning Patterns**:
- Persistent suicidal ideation
- Severe depression or anxiety symptoms
- Trauma processing
- Substance abuse patterns
- Eating disorder symptoms

**Frontend Response** (compassionate, not alarmist):
> "I notice you've been writing about [concern] quite a bit lately. This app is designed for self-exploration, not clinical support. It might be helpful to talk with a therapist or counselor who can provide professional guidance. Here are some resources..."

**Resources Provided**:
- NAMI (National Alliance on Mental Illness)
- SAMHSA helpline
- Psychology Today therapist finder
- BetterHelp/Talkspace (online therapy options)
- Local crisis lines

**Tone**:
- Non-judgmental
- Normalizing ("Many people benefit from professional support")
- Empowering ("You deserve professional guidance for this")

#### 7.3.3 Crisis Resources

**Crisis Detection** (limited AI capability, but flagging):
- If writing includes explicit statements of self-harm intent or suicidal plans
- Backend flags for immediate crisis resource presentation

**Immediate Response**:
> "If you're in crisis and need immediate support:
>
> **988 Suicide & Crisis Lifeline**: Call or text 988 (US)
> **Crisis Text Line**: Text HELLO to 741741
> **International Association for Suicide Prevention**: https://www.iasp.info/resources/Crisis_Centres/
>
> This app cannot provide crisis support. Please reach out to these resources—they're available 24/7."

**No AI Reflection Generated**:
- When crisis detected, skip standard reflection
- Only show crisis resources
- Follow-up: Gentle check-in next time user writes

#### 7.3.4 Limitations Acknowledgment

**Periodic Reminders** (monthly):
> "A note on what I can and can't do:
>
> ✓ I can help you notice patterns in your writing
> ✓ I can ask questions that prompt reflection
> ✓ I can organize your thoughts across time
>
> ✗ I can't diagnose mental health conditions
> ✗ I can't provide therapy or clinical treatment
> ✗ I can't understand context I haven't been given
> ✗ I can't replace human wisdom and connection"

**Epistemic Humility**:
- Explicit acknowledgment of AI limitations throughout
- "I might be missing important context"
- "Your lived experience is more complete than my pattern-matching"

---

## 8. Success Metrics

### 8.1 Engagement Metrics

#### 8.1.1 Daily Writing Consistency

**Primary Metric**: Writing frequency
- **Target**: 70% of users write 3+ days per week after first month
- **Measurement**: Count of entries per user per week
- **Segmentation**: By user cohort (week 1, month 1, month 3, month 6)

**Secondary Metrics**:
- Average writing duration (target: 10-30 minutes)
- Average word count (target: 300-1000 words)
- Writing time of day (understand user habits)

**Red Flags**:
- Declining frequency over time (indicates declining engagement)
- Very short entries (<100 words) consistently (may indicate low engagement)
- Writing only on weekly reflection days (gaming the system)

#### 8.1.2 Reflection Read Rate

**Primary Metric**: Percentage of reflections read
- **Target**: 80% of generated reflections opened within 48 hours
- **Measurement**: Reflection view events / reflections generated
- **Segmentation**: By reflection type (daily/weekly/monthly)

**Secondary Metrics**:
- Time spent reading reflection (target: 2+ minutes for daily, 10+ for weekly)
- Re-reading rate (users returning to past reflections)
- Scroll depth (do users read full reflection or just skim?)

**Red Flags**:
- Low open rates (<50%) indicates reflections not valuable
- Very short read times (<30 seconds) suggests lack of engagement
- Never re-reading old reflections (missing cumulative value)

#### 8.1.3 Feedback Interaction Rate

**Primary Metric**: Percentage of reflections receiving user feedback
- **Target**: 50% of reflections receive thumbs up/down or other feedback
- **Measurement**: Feedback events / reflections viewed
- **Segmentation**: By feedback type (binary, pattern-specific, open-ended)

**Secondary Metrics**:
- Positive vs. negative feedback ratio (target: 80%+ positive)
- Correction submission rate (shows engagement with quality)
- "Show reasoning" click rate (indicates curiosity about AI logic)

**Red Flags**:
- Very low feedback rate (<20%) suggests users aren't engaging critically
- Very high negative feedback (>30%) indicates poor reflection quality
- No corrections ever submitted (may indicate passive acceptance)

### 8.2 Quality Metrics

#### 8.2.1 User Satisfaction with Reflections

**Primary Metric**: Satisfaction survey (weekly/monthly)
- **Target**: 4+ out of 5 average rating on "This reflection felt accurate and helpful"
- **Measurement**: Post-reflection survey (optional but encouraged)
- **Questions**:
  - "This reflection felt accurate" (1-5)
  - "This reflection helped me see something new" (1-5)
  - "I felt understood" (1-5)

**Secondary Metrics**:
- Net Promoter Score: "Would you recommend this app?"
- Qualitative feedback themes (manually coded)
- Feature-specific satisfaction (questions, pattern identification, Playbook)

#### 8.2.2 "Doesn't Fit" Rate (Tracking Misaligned Interpretations)

**Primary Metric**: Percentage of hypotheses rejected by users
- **Target**: <10% rejection rate
- **Measurement**: Hypothesis rejections / hypotheses presented
- **Segmentation**: By hypothesis type, user cohort, time period

**Interpretation**:
- <5%: Possible over-agreement (lack of critical engagement)
- 5-15%: Healthy range (indicates collaborative testing)
- >15%: Pattern recognition quality issues

**Red Flags**:
- Increasing rejection rate over time (AI not learning)
- Same patterns repeatedly rejected (bad pattern matching)
- Zero rejections ever (suspicious, suggests passive acceptance)

#### 8.2.3 Pattern Validation Rate (User Agrees with Highlighted Patterns)

**Primary Metric**: Percentage of patterns confirmed by users
- **Target**: 60-80% confirmation rate
- **Measurement**: Pattern confirmations / patterns presented
- **Segmentation**: By evidence level (high/medium/low), pattern type

**Secondary Metrics**:
- Playbook addition rate (strong confirmation)
- Pattern modification rate (partial confirmation)
- Time to confirmation (immediate vs. after reflection)

**Interpretation**:
- <50%: Pattern recognition too speculative
- 50-80%: Good range (collaborative exploration)
- >90%: Possible confirmation bias or overly safe patterns

#### 8.2.4 Personal Playbook Adoption

**Primary Metric**: Percentage of users with 1+ Playbook items
- **Target**: 60% of users add to Playbook within first 3 months
- **Measurement**: Users with Playbook items / total active users

**Secondary Metrics**:
- Average Playbook items per user (target: 3-7)
- Playbook interaction frequency (views, updates)
- Evolution tracking engagement (do users review progress?)

**Red Flags**:
- Very low adoption (<30%) suggests feature not understood or valued
- Very high adoption (>90%) with no engagement suggests social desirability

### 8.3 Safety Metrics

#### 8.3.1 User Reports of Feeling Misunderstood

**Primary Metric**: Count of qualitative feedback indicating feeling misunderstood
- **Target**: <5% of users report feeling misunderstood
- **Measurement**: Manual review of open-ended feedback, support tickets
- **Keywords**: "Misunderstood," "not accurate," "off-base," "doesn't get me"

**Response**:
- Every report triggers review of that user's reflections
- Pattern analysis: Is misunderstanding systematic or one-off?
- Product improvements based on patterns in reports

#### 8.3.2 Over-Reliance Indicators

**Metrics to Monitor**:
- Time spent in app per day (target: <30 minutes on average)
- Number of times returning to reflections (healthy: 1-2x/day, concerning: 5+/day)
- User sentiment in writing about the app itself (looking for language suggesting dependency)
- Declining social connection references in writing over time

**Red Flags**:
- User writes extensively about AI reflections themselves (meta-loop)
- User describes app as "only thing that understands me"
- Dramatic increase in app usage during distress (using as emotional crutch)
- Writing frequency increases but content becomes repetitive

**Response**:
- Automated detection triggers boundary reminder
- Gentle suggestion to seek human connection
- Professional support resources offered

#### 8.3.3 Boundary Violation Reports

**Primary Metric**: Count of user reports that app overstepped boundaries
- **Target**: Zero reports of inappropriate content or overreach
- **Measurement**: Support tickets, in-app reports, qualitative feedback
- **Examples**:
  - AI claimed certainty inappropriately
  - AI used manipulative or emotionally intimate language
  - AI provided clinical advice
  - AI challenged affirmations

**Response**:
- Immediate investigation of reported reflection
- Review of generation process
- If confirmed: Public acknowledgment and correction
- Systemic changes to prevent recurrence

**Prevention**:
- Automated content filtering for prohibited language
- Regular audits of generated reflections
- Continuous prompt engineering refinement

---

## 9. Open Questions for Iteration

These are known unknowns that require user research, A/B testing, or iteration to resolve. Document is intentionally incomplete on these points.

### 9.1 Optimal Frequency for Hypothesis Disclosure Offers

**Question**: How often should the app offer to reveal hypotheses without being annoying or pushy?

**Current Approach**: "Show reasoning" always available, never auto-shown except in full transparency mode

**Open Questions**:
- Should app occasionally prompt "Curious about my reasoning?" after X reflections?
- Do users forget disclosure option is available?
- Is passive availability sufficient, or does app need to educate users about feature?

**Research Needed**:
- User interviews: Do they notice the disclosure option?
- A/B test: Occasional prompts vs. always passive
- Cohort analysis: Do users who try disclosure once continue using it?

### 9.2 Balance Between Challenge and Comfort in Weekly Reflections

**Question**: What's the right balance between supportive warmth and productive discomfort in weekly reflections?

**Current Approach**: Weekly reflections can include "growth edges" and tentative pattern confrontation, always with compassion

**Open Questions**:
- Do users want more challenge than current approach provides?
- Does challenge level need to adapt over time (more supportive early, more direct later)?
- How do different user types (secure vs. anxious attachment) respond to challenge?

**Research Needed**:
- Preference surveys: "This week's reflection was too gentle / just right / too challenging"
- Cohort analysis: Do users drop off after challenging reflections?
- Qualitative research: What makes challenge feel "productive" vs. "harsh"?

### 9.3 Personal Playbook UI/UX

**Question**: How should Playbook be visualized and interacted with?

**Current Approach**: Basic list format with status tracking and evolution notes

**Open Questions**:
- Should Playbook be visualized graphically (mind map, timeline)?
- How to balance complexity (rich pattern relationships) with usability (simple, scannable)?
- Should patterns show interconnections, or is that overwhelming?
- What makes users actually return to and use their Playbook?

**Research Needed**:
- Prototype testing: Multiple UI approaches
- Usage analytics: Do users revisit Playbook? How often?
- User interviews: "When do you look at your Playbook? What do you want from it?"

### 9.4 Integration with Existing Journaling Workflows

**Question**: How does this app fit into users' existing reflection practices?

**Current Approach**: Stand-alone app for writing and reflection

**Open Questions**:
- Should app integrate with existing tools (Day One, Notion, etc.)?
- Can users import existing journal entries for analysis?
- What if users want to write elsewhere and just get AI reflections?
- Should app support multiple "journals" (e.g., work vs. personal)?

**Research Needed**:
- User research: What are current journaling workflows?
- Competitive analysis: How do existing tools handle this?
- Technical feasibility: API integrations, import formats

### 9.5 Pricing and Monetization Approach

**Question**: How should this app be monetized in way that aligns with values?

**Current Constraints**:
- Cannot monetize through data (no selling user information)
- Must charge users directly

**Open Questions**:
- Subscription vs. one-time purchase vs. freemium?
- What features in free tier vs. paid tier?
- Pricing: $5/month? $10/month? $50/year?
- Should there be usage limits (e.g., reflections per month)?
- Student/low-income pricing tiers?

**Considerations**:
- Higher price signals quality and seriousness
- Lower price increases accessibility
- Subscription creates ongoing revenue but feels extractive
- One-time purchase aligns with values but limits sustainability

**Research Needed**:
- Willingness-to-pay surveys
- Competitor pricing analysis
- Cohort testing: Different pricing models for different groups

### 9.6 Temporal Rhythm: Are Daily/Weekly/Monthly the Right Cadences?

**Question**: Is the three-tier temporal structure (daily/weekly/monthly) optimal?

**Current Approach**: Daily (simple), weekly (deeper), monthly (trajectories)

**Open Questions**:
- Do some users want reflections after every entry (not daily batch)?
- Should there be bi-weekly reflections instead of/in addition to weekly?
- Is monthly too long—should there be 2-week reflections?
- Should cadence be user-configurable?

**Research Needed**:
- Usage patterns: When do users read reflections?
- Preference surveys: "I wish I got reflections more/less often"
- Cohort testing: Different temporal structures for different users

### 9.7 Multi-Modal Reflection: Voice, Video, Images?

**Question**: Should app support inputs beyond text writing?

**Current Approach**: Text-only (Morning Pages style)

**Open Questions**:
- Voice journaling: Speak instead of write?
- Photo capture: Visual journaling integration?
- Video logs: Self-recorded video reflections?
- Mixed media: Combine text + voice + images?

**Considerations**:
- Complexity increases dramatically with multi-modal
- Different reflection quality from different modalities
- Accessibility benefits (voice for users who struggle with writing)
- AI processing more complex and expensive

**Research Needed**:
- User demand: How many want non-text options?
- Prototype testing: Does voice journaling provide same value?
- Technical feasibility and cost

### 9.8 Social/Community Features (or Explicit Avoidance Thereof)

**Question**: Should there be ANY social dimension, or remain purely private?

**Current Approach**: Fully private, no social features (v1.0)

**Open Questions**:
- Anonymous pattern sharing: "X% of users notice this pattern too"?
- Opt-in community: Share reflections with trusted circle?
- Peer reflection: Request human feedback on patterns?
- Therapist sharing: Export reflections to share with actual therapist?

**Considerations**:
- Social features risk comparison, judgment, performativity
- Complete isolation may miss collaborative benefits
- Sharing with therapist could be valuable clinical tool

**Research Needed**:
- User demand: Do users want to share insights?
- Therapist interviews: Would they find AI reflections useful?
- Prototype testing: Opt-in community features with safeguards

### 9.9 Adaptation Over Time: How Should AI "Learn" User?

**Question**: How should AI's model of the user evolve over months/years?

**Current Approach**: Pattern tracking across time, feedback integration, evidence accumulation

**Open Questions**:
- Should AI become more direct/confident over time as it "knows" user better?
- Or should AI maintain same epistemic humility forever?
- How to handle when user changes (personal growth, life transitions)?
- Should there be option to "reset" AI's model of user?

**Considerations**:
- Increased confidence risks confirmation bias
- But perpetual tentativeness might feel unhelpful after months
- User change requires flexibility in AI model

**Research Needed**:
- Longitudinal studies: 6-12 month user experiences
- User interviews: "How has your relationship with the AI changed?"
- A/B testing: Adaptive confidence vs. consistent tentativeness

### 9.10 Reflection on Reflection: Meta-Insights About Growth Process

**Question**: Should AI help users reflect on their reflection practice itself?

**Current Approach**: Monthly reflections include some meta-commentary

**Open Questions**:
- Should there be quarterly "meta-reflections" about patterns in how users engage with reflection process?
- Progress dashboards: Visualize growth in self-awareness over time?
- Reflection style evolution: "Your writing has become more X over time"
- Help users see blind spots in what they journal about?

**Considerations**:
- Meta-layer valuable for self-awareness of self-awareness
- But risk of infinite regress (reflecting on reflecting on reflecting...)
- May feel too "meta" and intellectual vs. experiential

**Research Needed**:
- User interest: Do they want process-level insights?
- Prototype testing: Quarterly meta-reflections
- Value assessment: Does meta-reflection enhance growth?

---

## Appendix: Document Maintenance

### Version History

- **v1.0 (2026-02-06)**: Initial PRD created based on:
  - Research report on hypothesis disclosure (`research-hypothesis-disclosure-report.md`)
  - Reflection Framework v0.3 (`reflection-framework.md`)
  - Research brief (`research-brief-hypothesis-disclosure.md`)
  - 25+ peer-reviewed sources across therapeutic practice, cognitive psychology, and HCI

### Related Documents

- **Research Report**: `/04-projects/ai-assistant-app/resources/research-hypothesis-disclosure-report.md`
- **Reflection Framework**: `/02-personal/morning-pages-reflections/reflection-framework.md`
- **Research Brief**: `/04-projects/ai-assistant-app/planning/research-brief-hypothesis-disclosure.md`

### Future Iterations

This PRD should be updated based on:
1. User research and testing results
2. Technical feasibility discoveries during development
3. Stakeholder feedback and vision refinement
4. New research findings in therapeutic practice or AI ethics
5. Answers to open questions (Section 9)

### Feedback and Contributions

This is a living document. Suggested improvements, identified gaps, or new research findings should be:
- Documented in separate notes with rationale
- Discussed with project owner (Thanos)
- Integrated into next version with change log

---

*End of Product Requirements Document v1.0*

*This document represents the foundational requirements for the AI-Assisted Self-Reflection App as of February 6, 2026. It is grounded in research, informed by ethical principles, and designed to honor user autonomy while facilitating genuine self-discovery. Development should begin with core features (writing interface, daily reflections, basic pattern tracking) and iterate based on user feedback and research findings.*
