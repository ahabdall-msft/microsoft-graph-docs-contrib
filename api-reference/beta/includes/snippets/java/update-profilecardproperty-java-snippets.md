---
description: "Automatically generated file. DO NOT MODIFY"
---

```java

GraphServiceClient graphClient = GraphServiceClient.builder().authenticationProvider( authProvider ).buildClient();

ProfileCardProperty profileCardProperty = new ProfileCardProperty();
LinkedList<ProfileCardAnnotation> annotationsList = new LinkedList<ProfileCardAnnotation>();
ProfileCardAnnotation annotations = new ProfileCardAnnotation();
LinkedList<DisplayNameLocalization> localizationsList = new LinkedList<DisplayNameLocalization>();
DisplayNameLocalization localizations = new DisplayNameLocalization();
localizations.languageTag = "no-NB";
localizations.displayName = "Kostnadssenter";
localizationsList.add(localizations);
annotations.localizations = localizationsList;
annotationsList.add(annotations);
profileCardProperty.annotations = annotationsList;

graphClient.admin().people().profileCardProperties("CustomAttribute1")
	.buildRequest()
	.patch(profileCardProperty);

```