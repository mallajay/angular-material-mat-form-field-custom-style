### Angular Material mat-form-field custom style | Angular Material 18 | MDC

This repository provides a custom CSS styling guide for Angular Material form fields. The styles are specifically designed to enhance the appearance of the form fields by modifying the height, padding, border colors, text colors, and other visual elements.

The provided SCSS code customizes Angular Material form fields to improve their visual aesthetics. This includes:

- Modifying the height and padding of the form fields.
- Changing border colors for different states (focused, disabled).
- Customizing input text colors.
- Enhancing the appearance of filled form fields.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/mallajay/angular-material-mat-form-field-custom-style.git
   ```

2. Navigate to the project directory:

   ```bash
   cd angular-material-mat-form-field-custom-style
   ```

3. Install the necessary dependencies:

   ```bash
   npm install
   ```

### Usage

1. Add the CSS code to your Angular project's styles. You can include it in `styles.scss` or a specific component's SCSS file.
2. Use Angular Material form field components in your templates with the desired appearance:

```html
<div style="padding: 20px">
  <h5>1. Simple Outline Form Field</h5>
  <mat-form-field appearance="outline">
    <input matInput placeholder="Placeholder" />
  </mat-form-field>

  <hr />

  <h5>2. Form Field With Label</h5>
  <mat-form-field appearance="outline">
    <mat-label>Label</mat-label>
    <input matInput placeholder="Placeholder" />
  </mat-form-field>

  <hr />

  <h5>3. Form Field With Label, Hint & Icon</h5>
  <mat-form-field appearance="outline">
    <mat-label>Label</mat-label>
    <input matInput placeholder="Placeholder" />
    <mat-icon matSuffix>sentiment_very_satisfied</mat-icon>
    <mat-hint>Hint</mat-hint>
  </mat-form-field>

  <hr />

  <h5>4. Form Field With Select</h5>
  <mat-form-field appearance="outline">
    <mat-label>Favorite food</mat-label>
    <mat-select>
      <mat-option>Food 1</mat-option>
      <mat-option>Food 2</mat-option>
      <mat-option>Food 3</mat-option>
    </mat-select>
  </mat-form-field>

  <hr />

  <h5>5. Form Field With Date Picker</h5>
  <mat-form-field appearance="outline">
    <mat-label>Choose a date</mat-label>
    <input matInput [matDatepicker]="picker" />
    <mat-hint>MM/DD/YYYY</mat-hint>
    <mat-datepicker-toggle matIconSuffix [for]="picker"></mat-datepicker-toggle>
    <mat-datepicker #picker></mat-datepicker>
  </mat-form-field>

  <hr />

  <h5>6. Disabled Form Field</h5>
  <mat-form-field appearance="outline">
    <input [disabled]="true" matInput placeholder="Placeholder" />
  </mat-form-field>

  <hr />

  <h5>7. Filled Form Field Appearance</h5>
  <mat-form-field color="warn" appearance="fill">
    <input matInput placeholder="Placeholder" />
  </mat-form-field>

  <hr />

  <h5>8. Filled Form Field With Label</h5>
  <mat-form-field appearance="fill">
    <input matInput placeholder="Placeholder" />
  </mat-form-field>
</div>
```

This section provides a detailed explanation of the CSS code used to customize Angular Material form fields. The code is designed to enhance the visual appearance of the form fields by modifying various properties such as height, padding, border colors, text colors, and background colors.

#### Outline Appearance Customization

1. **General Customizations for Outlined Fields**

   ```scss
   .mdc-text-field--outlined {
     .mat-mdc-form-field-flex {
       /* Common customizations for both labeled and non-labeled fields */
       .mdc-notched-outline {
         height: 45px;
         padding-top: 10px;
       }

       .mdc-notched-outline--no-label {
         height: 45px;
         padding-top: 10px;
       }

       /* Customizing the border color of the leading, notch, and trailing parts */
       .mdc-notched-outline__leading {
         border-color: #026e78 !important;
       }

       .mdc-notched-outline__notch {
         border-color: #026e78 !important;

         .mdc-floating-label {
           cursor: inherit;
           top: 16px;
         }
       }

       .mdc-notched-outline__trailing {
         border-color: #026e78 !important;
       }
     }

     /* Customizing the input text color */
     .mat-mdc-form-field-flex .mat-mdc-form-field-infix .mdc-text-field__input {
       color: red;
     }

     /* Focused state customization */
     .mdc-text-field--focused {
       .mdc-notched-outline__leading {
         border-color: #5bdcc6 !important;
       }

       .mdc-notched-outline__notch {
         border-color: #5bdcc6 !important;
       }

       .mdc-notched-outline__trailing {
         border-color: #5bdcc6 !important;
       }
     }

    :focus-within .mdc-notched-outline,
    :focus-within .mdc-notched-outline__leading,
    :focus-within .mdc-notched-outline__trailing {
      border-color: #5bdcc6 !important;
      border-width: 1px !important;
    }
   }
   ```

   - The `mdc-text-field--outlined` class is used to target outlined form fields.
   - Within this class, the height and padding of the notched outline are set to 45px and 10px, respectively.
   - The border colors for the leading, notch, and trailing parts of the outline are customized to `#026e78`.
   - The input text color is set to red.
   - When the form field is focused, the border colors change to `#5bdcc6`.

2. **Disabled State Customization**

   ```scss
   .mdc-text-field--disabled {
     .mat-mdc-form-field-flex {
       .mdc-notched-outline__leading,
       .mdc-notched-outline__notch,
       .mdc-notched-outline__trailing {
         border-color: #201a1b1f !important;
         background: #73736b57;
       }
     }
   }
   ```

   - The `mdc-text-field--disabled` class customizes the appearance of disabled form fields.
   - The border color changes to `#201a1b1f`, and the background color is set to `#73736b57`.

#### Filled Appearance Customization

1. **General Customizations for Filled Fields**

   ```scss
   .mdc-text-field--filled {
     background-color: #fff !important;
     height: 40px;
     padding-left: 3px;

     .mat-mdc-form-field-flex .mat-mdc-form-field-infix {
       padding-top: 10px;
       padding-bottom: 10px;

       /* Input text color and font size customization */
       .mdc-text-field__input {
         color: blue;
         font-size: 12px;
       }
     }

     /* On hover, change the background color */
     .mat-mdc-form-field-focus-overlay {
       background-color: green !important;
     }

     /* Change the border bottom color */
     .mdc-line-ripple::before,
     .mdc-line-ripple::after {
       border-bottom-color: blue !important;
     }
   }
   ```

   - The `mdc-text-field--filled` class is used to target filled form fields.
   - The background color is set to white, height to 40px, and left padding to 3px.
   - The input text color is set to blue, and the font size is set to 12px.
   - On hover, the background color changes to green.
   - The bottom border color is customized to blue.

By applying these customizations, you can significantly enhance the visual aesthetics of Angular Material form fields in your application.


For a hands-on example and to see these styles in action, visit the [live demo on StackBlitz](https://stackblitz.com/~/github.com/mallajay/angular-material-mat-form-field-custom-style).
