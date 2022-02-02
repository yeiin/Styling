# Styling

learn styling react

Goal: Add dynamic styling differently than css

- trim() : removes excess white space at the beginning or the end.
- inline style : The css code which is short in HTML code.

- Way 1
  import styled from "styled-components";
  const Button = styled.button`
  font: inherit;
  padding: 0.5rem 1.5rem;
  border: 1px solid #8b005d;
  color: white;
  background: #8b005d;
  box-shadow: 0 0 4px rgba(0, 0, 0, 0.26);
  cursor: pointer;

  &:focus {
  outline: none;
  }

  &:hover,
  &:active {
  background: #ac0e77;
  border-color: #ac0e77;
  box-shadow: 0 0 8px rgba(0, 0, 0, 0.26);
  }
  `;

- Way 2 
  import React from "react";
  const Button = props => {
  return (
  <button type={props.type} className="button" onClick={props.onClick}>
  {props.children}
  </button>
  );
  };

- Way 3
  - .module.css
    This is basically a signal to the underlying compilation process to transform to code so that css modules work.
   
  - import styles from './CourseInput.module.css'
  - <div className={styles['form-control']}>
        <label>Course Goal</label>
        <input type="text" onChange={goalInputChangeHandler} />
      </div>


- Parasing error: adjacent JSX elements must be wrpped in an enclosing tag. Did you want a JSX fragment..?
  - must have one root elements.