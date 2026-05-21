# Getting Started

1. Install the plugin. See [Installation](installation.md) for details.

2. Ensure the plugin is enabled in the editor:

   ![Plugin enabled in editor](assets/Beta_Plugin_Enabled.png)


3. Create a Blueprint Class of type `ExampleController`:

   ![Controller in editor](assets/ExampleCTEditor.png){ align=center }

   It should look like this:

   ![Example Controller in Editor](assets/ECT_Window.png)

4. For the Planner Component to work, you'll need some actions. Create a Blueprint of type `Action`:

   ![Action in Editor](assets/Action_BP.png){ align=center }

   It should look like this:

   ![Action Window BP Editor](assets/Action_Window.png){ align=center }

5. Click on **Class Defaults**. You should see something like this:

   ![Action Class Defaults](assets/Action_Class_Defaults.png)

   This is where you define:

   - **Action Name**
   - **Cost**
   - **Preconditions**
   - **Effects**

   **Preconditions** determine what must be true (or false) before the action can be executed.

   **Effects** determine what becomes true (or false) after the action has been performed.

   Here’s an example of an action where the AI might be dancing, but without any preconditions:

   ![Action precondition example](assets/A_Precodition.png){ align=center }

## Action Execution Override

This is where you define how the action behaves during execution.

1. Left-click **Functions Overridable**.
2. Hover over the overridable function list until you see this:

   ![Override function](assets/Action_Execute.png)

3. Click **Execute**.

You should see an [`EExitSequenceType`](API_ref/exit_sequence.md) input along with an `Owner` input of type `Actor`.

If you are using the example controller, `Owner` will almost certainly be an `AIController` / `ExampleController`, so you can safely cast it.

`Owner` is typed as `Actor` so users who place their Planner and Reasoner Components directly on the character (instead of the controller) can still use the same execution flow.

Now you can implement the action's functionality.

If you're unsure what this should look like, see the example below:

### Example Action: Set Material and Teleport AI

<iframe
    src="https://blueprintue.com/render/p-d1f-r9/"
    width="900"
    height="400"
    scrolling="no"
    allowfullscreen>
</iframe>