# Beautiful Skill Tree

A small library to help get you implement beautiful, responsive, and satisfying skill trees to your React applications

---

## Examples

[Calisthenics Progressions](https://calisthenicsskills.com/)

---

## Getting started

`yarn add beautiful-skill-tree`

The package exposes three components `SkillTree`, `SkillTreeGroup` and `SkillProvider`.

The `SkillTree` is the component that takes your data and renders the tree of components.

The `SkillTreeGroup` is the component that groups skill trees and will expose in the future expose various methods and properties related to the skill tree.

The `SkillProvider` is the skill tree's context provider.

For those that like their data typed, you can import `SkillType` from the package.

Wrap your application like this:

```typescript
import { SkillTreeGroup, SkillTree, SkillProvider, SkillType } from 'beautiful-skill-tree';

const data: Skill[] = [];

<SkillProvider>
  <SkillTreeGroup>
    {skillCount => {
      <SkillTree treeId="first-tree" title="Skill Tree" data={data} />
    }}
    </SkillTreeGroup>
<SkillProvider>
```

Run your application's starting script and access localhost to find an empty skill tree. The skill tree group will be empty until data is passed to the skill tree.

Add the following data to your skill tree and see what happens:

```typescript
const data: Skill[] = [
  {
    id: 'hello-world',
    title: 'Hello World',
    tooltipDescription:
      'This node is the top most level, and will be unlocked, and ready to be clicked.',
    children: [
      {
        id: 'hello-sun',
        title: 'Hello Sun',
        tooltipDescription:
          'This is a parent of the top node, and will locked while the parent isn’t in a selected state.',
        children: [],
      },
      {
        id: 'hello-stars',
        title: 'Hello Stars',
        tooltipDescription:
          'This is the child of ‘Hello World and the sibling of ‘Hello Sun’. Notice how the app takes care of the layout automatically? That’s why this is called Beautiful Skill Tree and not just ‘Skill Tree’. (Also the npm namespace had already been taken for the latter so (flick hair emoji).',
        children: [],
      },
    ],
  },
];
```

Go to your browser and you should see this:

![Skill Tree Demo](https://media.giphy.com/media/j2qzDGItebWCtFA7lW/giphy.gif)

---

## Motivation

Is there anything more satisfying than the feeling of progression; you know, improving at something you care deeply about? Not likely! Be it in video games, web development, or your physical capabilities, very little gives us a sense of pride and accomplishment than gaining new skills and using them. My motivation was to make skill trees that feel satisfying and fun to use.

Unfortunately there aren't any React packages that enable us developers to easily create skill tree in their applications. This is where Beautiful Skill Tree comes in. BST is a small package that allows you to easily create your own skill trees that look great across devices and screen sizes.

---

## Component API

### SkillTree

#### treeId: `string` [*required*]

#### title: `string` [*required*]

#### data: `SkillType` [*required*]

### SkillTreeGroup

#### children: `(treeData) => React.ReactNode` [*required*]

### SkillProvider

### SkillType

```typescript
type SkillType[] = {
	id: string;
	title: string;
	tooltipDescription: string;
	icon?: string;
	children: SkillType[];
}
```

### TreeData

```typescript
type TreeData = {
  skillCount: number;
  selectedSkillCount: number;
  resetSkills: () => void;
};
```

---

## V1 Checklist

- [x] Skill
- [x] Animations
- [x] Progress saving
- [x] Tooltips
- [x] Icons
- [x] Responsive
- [x] Expose skill tree state
- [x] Reset skill tree
- [ ] CSS theming
- [ ] Optional nodes
- [ ] Side nodes
- [ ] Collapsable skill trees
- [ ] Keyboard only use
- [ ] Secret special surprise on tree completion

---

## Contributing

[contributing guidelines](/CONTRIBUTING.md)

### Contributors

[Andrico Karoulla](https://github.com/andrico1234)
[Juan Melendez](https://github.com/juanmanual)
