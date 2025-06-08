# FlowDSL VS Code Extension

FlowDSL is a domain-specific language for authoring node-based game logic.  
This extension adds syntax highlighting for files with the `.flow` extension so you can read and edit FlowDSL sources comfortably in VS Code.

## Features

The grammar recognizes node labels, node types, parameters, string and numeric literals, comments, the arrow operator, and indentation-grouped child nodes.  
It is designed to make complex branching structures, dialogue trees, and data-flow graphs readable at a glance.

## Installation

1. Build the extension package with `vsce package`.  
   This creates a file named `flowdsl-<version>.vsix` in the project root.  
2. Install it in VS Code with `code --install-extension flowdsl-<version>.vsix`.  
3. Reload VS Code. Any file ending in `.flow` will now use the FlowDSL grammar automatically.

## Example

```flow
player_node: Player(name="Aria", hp=120)
intro: Dialogue("You awake in a dark forest.") -> choice

choice: Choice("What will you do?")
    fight: Combat(enemy="Wolf", hp=40)
    flee:  Escape(destination="Village")
