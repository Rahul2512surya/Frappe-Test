const previousComponents = issue.changelog?.components?.from || [];
const currentComponents = issue.components || [];

// Find components that were actually added
const newlyAddedComponents = currentComponents.filter(
  component => !previousComponents.some(
    previous => previous.name === component.name
  )
);

// Trigger story creation only for newly added supported components
const supportedComponents = [
  "Rio - OMS",
  "Rio - 1P",
  "Rio - Monetization"
];

const componentsToCreateStoriesFor = newlyAddedComponents.filter(
  component => supportedComponents.includes(component.name)
);

if (componentsToCreateStoriesFor.length > 0) {
  // Create story only for newly added component
}
